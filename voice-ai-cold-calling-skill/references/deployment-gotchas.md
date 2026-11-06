# Voice Platform Deployment Gotchas

Framework-agnostic traps that show up when wiring a calling agent into a voice platform. These were learned the hard way in deployment and each one produces a failure that's obvious in hindsight and invisible until it costs you calls.

---

## 1. The Opening Line Is Usually a Separate Field

Most platforms have a **greeting/welcome message** configured independently of the system prompt. It fires first, before the agent's prompt has any influence.

If your prompt opens with "Hi, I'm calling about…" but the greeting says "This call may be recorded, this is [Entity]…" — those are two different opens and the second one is what the recipient actually hears.

**Fix:** treat the greeting as the canonical opener. The system prompt should begin *after* it and any state that assumes "the call has started" needs to account for the greeting already having spoken.

---

## 2. Queued Speech Is Not Interruptible

If the platform buffers a response and plays it after the recipient has already spoken over it, you get the worst possible failure: talking over a human who was mid-sentence.

**Fix:** set the first response to interruptible and configure barge-in so a recipient speaking cuts off agent speech. Verify this on a real call, not in a test — many platforms behave differently once real latency is present.

---

## 3. Streaming Latency Changes Everything

A streaming response starts speaking in ~300ms; a non-streaming one takes 1–3s. In a live conversation that difference is the difference between "responsive" and "is this thing even connected?"

**Fix:** stream. Push each completed clause to the synthesiser as it arrives rather than waiting for the full response. `technique-01` explains why flushing on punctuation beats waiting for the whole sentence.

---

## 4. Synthetic Voices Are Detected Within Three Seconds

If the recipient can tell it's synthetic in the opening line, the rest of the call is already lost.

**Fix:** accept small latency in exchange for natural prosody. Slower, more human-sounding speech beats fast robotic speech. Where a platform supports it, prefer a voice matched to the persona's described tone rather than the fastest available one.

---

## 5. "Local" and "Home Service" Narrow Your Audience

Words like "local businesses" and "home services" appear in the opening and implicitly exclude everyone else. Med spas, law firms, schools and consultancies hear "not for me" and disengage.

**Fix:** remove them from the opening and the identity sections. Describe the *problem* you're solving, not the demographic you serve. See `live-call-quality-rules.md` Rule 1.

---

## 6. "We'll Call You Back" Loses Urgent Leads

When someone says they need help now, a callback offer reads as not listening.

**Fix:** offer live escalation if you have it; otherwise give a specific short timeframe rather than "in 24 hours". See Rule 4.

---

## 7. Transcriptions Fail Differently Than You Expect

Recognition errors cluster on specific words: names, numbers and domain terms ("available", "financial", brand names). Errors are also *fluent* — "I'm free in the evening" → "I'm feeling dizzy" produces a perfectly plausible sentence.

**Fix:** confirm before acting on anything contextually surprising. Add known product and brand terms to the recognition vocabulary. Never let transcription alone trigger consequential actions — see Rule 5.

---

## 8. Test the Failure Paths, Not Just the Happy Path

The happy path works. What breaks in production is the LLM timing out mid-call, the synthesiser failing on an unusual character or a tool call erroring.

**Fix:** every deployment needs an explicit, tested fallback — apologize, offer a callback number, hang up cleanly. A graceful failure is worth more than a clever success, because it also happens at 3am to someone who just needs the phone to stop.

---

## 9. Turn Latency Is a Configuration Choice

Newer models reason well but think slowly. That cost shows up as dead air.

**Fix:** tune the reasoning budget to the task. Straightforward turns need almost none. Reserve longer reasoning for the moments that warrant it — pricing questions, unusual objections, anything where a wrong answer would be costly.

---

## 10. Single-Question Turns, Always

Asking two questions in one turn reliably loses the second one. On a voice call people also can't scroll back, so a lost question is just gone.

**Fix:** one question per turn. If two are needed, ask the first, get the answer, then ask the second. This reads as attentive rather than overwhelming.

---

## 11. Rate Limits Degrade Quietly

Hitting a provider rate limit often manifests as a slower response or a truncated answer rather than an error, so calls keep "succeeding" while quality drops. You won't notice from the logs.

**Fix:** measure response latency per turn, not just call completion. Alert on the latency distribution, not the error rate.

---

## 12. Numbers Spoken Aloud

Reading "800" as "eight hundred" and "$1,600" as "sixteen hundred dollars" sounds markedly more human than digit-by-digit or symbol-heavy delivery.

**Fix:** normalize currency and number formatting in the text sent to the voice engine, not in the text sent to the LLM. The model should reason about "1600"; the synthesiser should hear "sixteen hundred".

---

## Pre-Launch Verification

- [ ] Greeting field and system prompt agree on the opener
- [ ] Barge-in verified on a real call, not a test
- [ ] Streaming enabled, first audio latency acceptable
- [ ] Voice matches the persona's tone
- [ ] No "local"/"home service" phrasing in opening or identity
- [ ] Escalation path for urgent requests
- [ ] Domain vocabulary added to recognition
- [ ] LLM-failure fallback tested
- [ ] Reasoning budget tuned per turn complexity
- [ ] One question per turn
- [ ] Numbers and currency normalized for speech
- [ ] Per-turn latency monitored and alerting