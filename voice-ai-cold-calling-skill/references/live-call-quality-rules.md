# Live Call Quality Rules

Six rules extracted from reviewing real agent calls. These are **not**
conversation techniques — they're quality guardrails that apply to every outbound
call regardless of which technique you loaded.

Read these before any call. Most disappointing calls fail on these, not on
technique selection.

---

## Rule 1 — Bridge the Industry Gap

**When:** the recipient's business sits outside your primary vertical.

**Why it matters:** opening with a narrow vertical framing makes everyone outside
it feel like an afterthought. They hear "wrong type of caller" and disengage
before you've said anything useful.

**The trap:** using "local businesses", "home services" or "we mainly work
with [vertical]" in the opener. Every one of those narrows who will keep
listening and the ones it excludes are the ones you can't help.

**Fix:** acknowledge the gap, then bridge.

```
"Most of the people we work with are [primary vertical], but what you're
describing — [their actual situation] — that's exactly the kind of thing we
help with. Can I ask you a couple of quick questions?"
```

And drop those qualifier phrases from the opening and identity sections entirely.

---

## Rule 2 — Probe, Don't Pivot

**When:** they mention they already have a solution.

**Why it matters:** immediately abandoning that thread is the single most obvious
sign you're reading a script. It also throws away the best qualification signal
on the call.

**Fix:** probe for the gap before moving on.

```
"Oh nice — how's that working out? Are there gaps or things you wish it did
better?"
```

Even if the answer is "it's fine", you've demonstrated genuine curiosity, and
they've now thought about the gap themselves. That question builds more trust
than five minutes of pitching.

---

## Rule 3 — Pitch Only What's Relevant

**When:** they have one clear need and you're about to describe everything you do.

**Why it matters:** reciting a service list is the most reliable way to sound
automated. It also proves you weren't listening, which matters more — people
decide whether to trust you in the first ninety seconds and this is a direct
contradiction of anything they just told you.

**Fix:** summarise their need first, then present only that.

```
"Based on what you've told me, the biggest thing you're dealing with is [X].
Here's how we handle [X] specifically..."
```

| They said | Pitch |
|-----------|-------|
| Missing calls/no answer | Call answering |
| Not showing up in search | Visibility |
| Slow response to enquiries | Speed to lead |
| Nothing specific yet | Stay in discovery — don't pitch at all |

---

## Rule 4 — Respect Urgency

**When:** they say "I need this sorted now" or "put me through to someone".

**Why it matters:** offering a callback to someone who needs help *now* reads as
you not listening. It's also where you most obviously lose the deal.

**Fix:** acknowledge and escalate or compress the timeline.

```
"I completely understand. Let me see if I can get someone onto this now. If I
can't reach them straight away, you're first on the list and they'll call you
within the hour. Fair?"
```

If you genuinely can't transfer, say so plainly and give a *specific short*
timeframe. "Within the hour" versus "in 24 hours" is the whole difference —
you're not promising more, just signaling you heard the urgency.

---

## Rule 5 — Confirm Suspect Transcriptions

**When:** what you heard seems contextually wrong — especially something sudden
or medically concerning.

**Why it matters:** speech recognition produces confident nonsense. "I'm free
this evening" transcribing as "I'm feeling dizzy" can send an agent into a
health response it has no business giving.

**Fix:** confirm before acting.

```
"Just to check — did you say you're free this evening for a callback?"
```

**Never** launch into a health, crisis or emergency response. You are not
qualified, not insured and not a monitored service. Sympathize briefly and
point to emergency services where appropriate. See
`outbound-compliance.md` on data you must never collect.

---

## Rule 6 — Referral Ask on Every Exit

**When:** any call ending — interested, maybe or no.

**Why it matters:** a referral ask costs one sentence and is the cheapest lead
source available. The worst they can say is no and they already know you.

**Fix:** vary it by outcome.

| Outcome | Ask |
|---------|-----|
| Interested | "One last thing — do you know anyone else who'd find this useful?" |
| Maybe/not now | "If you hear of anyone else interested, send them our way." |
| Not interested | "No problem. Do you know anyone else who might have this problem?" |

**On surveys, don't.** In genuine research the ask biases participation and
misdirects the sample — see `technique-04-survey-and-inquiry.md`.

---

## Additions From Live Review

### Rule 7 — Don't Fill Every Pause

Silence is processing, not failure. An agent that talks to avoid a gap sounds
anxious. Let them finish. Count to three before you speak.

### Rule 8 — Vary the Opening Across Calls

Identical phrasing across a batch is how people clock the agent as automated in
the first three seconds. Have 3–5 opening variants and rotate them. The content
stays the same; only the surface varies.

### Rule 9 — Acknowledge Then Move

When they say something that deserves a response, give one sentence and move on.
"I can imagine that's frustrating" followed by the next question beats either
ignoring it or dwelling on it.

### Rule 10 — Know When to Stop

A polite exit after 90 seconds beats a dead air call at six minutes. If the two
close attempts don't land, close anyway and record the disposition. Leaving a
polite voicemail is a better outcome than talking past the point of usefulness.

### Rule 11 — Never Inherit Another Offer's Language

**When:** configuring or reviewing a pitch.

**Why it matters:** this is the most common and most damaging configuration
error. Questions and phrasing carry the assumptions of the offer they were
written for and transplanting them makes the agent ask something absurd — or
worse, something that reveals it isn't listening.

"How many calls do you miss?" is a strong question for a missed-call offer and
disqualifying nonsense for a property assessment or a debt recovery call.

**Fix:** questions live in the **pitch record**, chosen by `offer_type` from the
bank in `technique-01-research-survey.md`. Nothing offer-specific belongs in a
technique file. See `pitch-type-routing.md`.

### Rule 12 — Say One True Thing, Then Ask

**When:** the opening, especially on a call with no prior relationship.

**Why it matters:** cold-call recipients have learned to filter unknown calls by
their first sentence. Vagueness reads as a sales call and gets filtered; one
specific, verifiable fact reads as genuine and buys you thirty seconds.

**Fix:** a real detail about their situation, then a question.

```
"You recently [verifiable thing] — I wanted to ask about [topic]. Is this a
bad moment?"
```

**Never** manufacture familiarity. Inferring a team size, a revenue figure or a
problem they never mentioned is the fastest way to lose the call and it reads
as a scam to anyone paying attention.

### Rule 13 — One Pitch Per Call

**When:** a campaign covers more than one offer or the recipient seems like a
fit for a different one.

**Why it matters:** switching offers mid-call is audible. The vocabulary,
questions and pace all shift and recipients can hear the config change. It
converts a credible call into an obvious automated one.

**Fix:** route by segment before the call starts. If the agent genuinely
discovers a better-fitting offer mid-call, treat it as a **referral to another
call**, not a pivot: "That's actually a different conversation — can I pass that
to the team?"

### Rule 14 — Match the Register, Not the Script

**When:** you've noticed who you're talking to.

**Why it matters:** the same content lands differently depending on the person.
A technically precise buyer hears vagueness as unpreparedness; a non-technical
buyer hears precision as a sales tactic.

| They're | Deliver |
|---------|---------|
| Short answers, impatient | Point first, one question, offer a fast exit |
| Long, detailed | Follow up properly. Don't rush the close |
| Technically precise | Be precise. No hedging |
| Non-technical | Plain language, no acronyms, fewer numbers at once |
| Price-driven early | Isolate the real objection before quoting |
| Skeptical, asks who you are | Disclose plainly, then move to their problem |

**Two adjustments maximum.** Changing register more than twice feels manipulative.