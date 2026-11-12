# Technique 01 — Research Survey

**Best for:** cold outbound calls and first contact with someone who has no
prior relationship.

**When NOT to use:** post-demo follow-ups (`technique-02`), reviving a known lead
(`technique-03`), genuine survey work (`technique-04`).

**Source:** Katon Walker — cold calling research-first demo.

---

## Core Philosophy

**"Do research, not sales."**

Frame the call as a short investigation rather than a pitch. This lowers the
recipient's guard and yours. You stop making claims and start asking questions.

It works because it's honest. Someone who feels sold *to* gives short,
defensive answers. Someone who feels *asked* tells you what's actually true —
including whether they're a fit at all, which is often not.

**Corollary:** the recipient should be talking 60–70% of the call. If you're
talking more than that, you're pitching.

**Why "research" is genuinely the right frame:** it's also the most honest
framing available for a cold call, which matters because recipients probe.
"What's this really about?" gets a straight answer and the answer is true.

---

## The Opener

```
"Hi, my name is [Name] from [Entity]. Bit of an unexpected call — I'm looking
into [specific situation in their world]. A couple of quick questions, about
[time] minutes. Is now a good time?"
```

Four elements doing the work:

| Element | Why |
|---------|-----|
| "bit of an unexpected call" | Self-aware; acknowledges the interruption |
| "looking into [their situation]" | Research framing and specific to them |
| "a couple of quick questions" | Low stakes, bounded |
| "[time] minutes" | Specific and small |

The middle element is where the **pitch config** plugs in. It must describe
something true about *their* world, not about your offer. See
`persona-and-pitch-design.md`.

### If They Hesitate

```
"It's genuinely just about [topic]. Nothing to buy — I'd rather find out if it's
even relevant than pitch you something you don't need."
```

### If They Say No

```
"No worries at all — thanks for your time."
```

Then, only if the conversation was warm:

```
"Actually, do you know anyone else in [their world] who'd have a couple of
minutes?"
```

---

## The Question Bank

**This is the pitch-agnostic core.** The questions that work for a missed-calls
offer are nonsense for an EPC retrofit survey, a software license or a debt
recovery call. The bank below is organized by *purpose*, so the pitch config
selects from it rather than inheriting one offer's questions.

Choose **2–4**. Ask about their situation, never about your product.

### Opening — establish relevance

| Purpose | Question |
|---------|----------|
| Confirm fit | "Before I ask anything — is [company] still [what they do]?" |
| Establish scale | "Roughly how many [their unit of work] would you say you handle in a typical week/month?" |
| Establish context | "How are things going with that at the moment?" |

The fit question is not small talk. It catches wrong numbers, closed
businesses and wrong-person calls before you spend their time.

### Diagnosis — find the friction

| Purpose | Question |
|---------|----------|
| Locate the gap | "Where does [process] usually go wrong, if at all?" |
| Quantify frequency | "How often does that happen?" |
| Quantify scale | "What does that cost you each time it does?" |
| Find workarounds | "What do you do about it now?" |

The workarounds question is the most diagnostic one. What someone has already
built to cope tells you what they actually value and it's more reliable than
what they say they'd like.

### Consequence — establish the cost

| Purpose | Question |
|---------|----------|
| Time cost | "How much of someone's week does that take up?" |
| Money cost | "What does that end up costing you?" |
| Knock-on | "And what does that lead to, further down?" |
| Risk cost | "What's the worst that could happen if that goes wrong?" |

Knock-on is the question that finds the real number. Most people quote the
obvious cost and then, after a pause, describe the larger one.

### Context — make it theirs

| Purpose | Question |
|---------|----------|
| Prior attempt | "Have you tried anything to sort that out?" |
| Decision path | "Who else would need to be happy with this?" |
| Timing | "Is there a reason it's come up now?" |

Timing is often the single most useful question in a cold call. "It's come up
now" reveals a trigger — an event, a deadline, a failure — which changes the
whole approach.

---

## Configuring the Bank Per Pitch

Each pitch record names which questions apply, in the pitch's own vocabulary.
Two examples, same structure:

**Lead-response offer:**
```yaml
opening:    ["fit", "scale: calls per week"]
diagnosis: ["gap: missed or unanswered", "frequency", "cost per lost enquiry"]
consequence: ["money: value of a new customer", "knock-on"]
context:    ["prior attempt: existing answering service", "timing"]
```

**Retrofit assessment offer:**
```yaml
opening:    ["fit: owns the property", "context: when did you get the certificate?"]
diagnosis:  ["gap: what's flagged in it", "frequency: has anything been done about it"]
consequence: ["money: what improvements would it add", "knock-on: running costs"]
context:    ["prior attempt: previous installer quotes", "timing: any deadline?"]
```

**On translating vocabulary:** if they say "call handling" and the pitch says
"response rate," use *their* phrase. Mirroring builds rapport and avoids a
correction turn that wastes a question. See `conversational-core.md`.

---

## The Pause Question

Sometimes the sharpest data comes when you stop prompting:

```
"I've asked a lot — what am I missing?"
```

This often surfaces the real objection that polite respondents withheld. Use it
once, late and don't use it if the call is going badly.

---

## Pain Math

After you've found a pain with a cost, say the arithmetic out loud. Their
numbers, their currency, rounded to something a person would actually say.

```
"So if that's happening [frequency] and it costs about [value] each time, that's
roughly [total]. Does that sound about right?"
```

**Rules that make it credible:**

- Use their figures, even rough ones
- Round naturally — "about sixteen hundred a week", not "1,600.00"
- Ask for confirmation, then stop
- If they dispute it, listen. They're telling you their model is different

**When the pain isn't financial,** route to time or risk instead — hours lost,
exposure created, deadline pressure. See `pricing-and-positioning.md` for the
full translation methods. Not every offer is quantifiable in money on a cold
call and forcing currency onto something intangible is what makes pain math feel
like a gimmick.

---

## The Soft Pivot

Only after the pain is named and quantified:

```
"That's a real cost to be carrying. The reason I asked, honestly — we help with
[specific capability] and I wanted to find out whether it's even relevant to you
before saying anything more about it."
```

The framing that works: you're checking relevance, not pitching. It gives them a
way to say "not relevant" without awkwardness — and people are often more willing
to give a short answer than to guess where the call is going.

---

## Objection Handling

| Objection | Response |
|-----------|----------|
| "Already have a solution" | "How's that working? Are there gaps or things it doesn't do?" |
| "We handle that ourselves" | "That makes sense. How long does it take you and what happens if it doesn't happen?" |
| "Not the decision maker" | "No problem — is there someone else who'd be better to talk to?" |
| "Not comfortable sharing that" | "Totally understand — no worries at all." |
| "Too small/not relevant yet" | "Fair enough. Do you know anyone else who might have this problem?" |
| "Is this a sales call?" | "It started as research. I can tell you honestly whether we're relevant or leave it there — either way." |
| "How much is it?" | See pricing reference — isolate before quoting |

**"We already handle that":** don't argue. Ask what it costs them in time or
attention. Self-handled processes are almost always under-priced in the
recipient's own time and the question is usually enough.

---

## The Close

One ask. Then stop talking.

```
"Sounds like this could be worth a proper look. Would [day, time] or [day, time]
suit for a conversation with the team?"
```

- **Two concrete options, not an open question.** "When should we call back?"
  gets "I'll think about it." Two options get an answer.
- **Confirm before hanging up.** Read the time back.
- **If they hesitate:** "No pressure. Would it help if I sent a couple of
  details to look at?"
- **If they decline:** thank them, ask for a referral if warm, hang up.

Don't negotiate price on a first call. You haven't earned it and discounting
signals the number was inflated.

---

## Why This Works

1. **It doesn't feel like a pitch**, so they stay on the line.
2. **It's honest**, so it survives a direct probe.
3. **It qualifies in both directions** — you find out if they can use what you
   sell and they get an honest answer about relevance.
4. **It produces usable data** — discovery answers are more reliable than
   closing answers.
5. **It scales** — a short, low-friction call can be made hundreds of times
   without burning bridges.

---

## Common Failure Modes

| Failure | Cause | Fix |
|---------|-------|-----|
| Hung up immediately | Opener too long or pitchy | Name, reason, bound, permission — in that order |
| "What is this about?" | Pitched before establishing relevance | Lead with the research framing |
| Questions felt irrelevant | Bank questions taken literally | Select per pitch from the bank, translate to their words |
| Long call, no next step | Never reached a close | One ask, two concrete time options |
| Talked too much | Discovery skipped | If you haven't had two real answers, you haven't discovered |
| Pitched something irrelevant | Assumed rather than confirmed | Present only what matches what they described |
| Pain math fell flat | Forced currency onto an intangible | Use time or risk instead |