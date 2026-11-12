# Objection Matrix

A coverage map for auditing objection handling. Most agents handle the four or five obvious objections and fall over on the rest.

Use it to find gaps, not to fill in every cell. An agent reciting twenty objections sounds like a script. Handle the common ones behaviorally and let the model generalize from a few principles.

---

## The Four That Matter Most

| Objection | Real meaning | Response shape |
|-----------|--------------|----------------|
| "Not interested" | Not interested *as framed* | Re-frame, once. If still no — exit. |
| "Too expensive" | Unclear: number or vs. expectation? | Isolate before responding |
| "I'm not the right person" | Legitimate | Get the name or get a referral |
| "Send me an email" | Soft yes or soft no | Confirm the address, set a follow-up time |

Everything else is a variation on these.

---

## Coverage Matrix

| Category | Objection | Response |
|----------|-----------|----------|
| **No time** | "I'm busy" | "Completely fine — what time works better?" |
| | "I'm driving" | Never continue. "Pull over safely, I'll call back — when?" |
| | "I'm in a meeting" | Offer a specific later slot |
| **Authority** | "I'm not the owner" | "Who would be best to speak to?" |
| | "I don't know" | Ask for the name anyway |
| | "They're in a meeting" | Ask when they're free |
| **Budget** | "No budget" | "How about we have a conversation first that is not about the money?" |
| | "Need approval" | "Who signs it off?" |
| **Timing** | "Not right now" | "When would be better?" |
| | "Come back next year" | Offer a specific date or long-term suppression |
| **Status** | "Already have a supplier" | "How's it working? Any gaps?" |
| | "Just started looking" | Early stage — stay in discovery |
| | "We've solved this" | Ask how, look for the residual problem |
| **Objection to AI** | "I don't want a robot" | Offer a human handover if you have one |
| | "A machine can't do X" | Agree about the job — offer capture, not replacement |
| **Trust** | "Are you a bot?" | Disclose truthfully |
| | "Is this a sales call?" | Answer honestly |
| | "How did you get my number?" | Answer factually; never improvise |
| **Compliance** | "Remove me" | Confirm, apologize, hang up. No questions. |
| | "Stop calling" | Same, immediately |
| **Logistics** | "Send me details" | Confirm the address and a follow-up time |
| | "Send an email" | Confirm, then set a specific call-back date |

---

## Principles That Generalize

Better than an exhaustive list, because they cover cases you didn't list:

**Isolate before responding.** "Too expensive" and "not in the budget" produce opposite responses. One clarifying question separates them.

**Never argue.** Every attempt to talk someone out of an objection makes it stronger. Change the frame or move on.

**One re-frame, maximum.** After a second attempt, accept the answer and close. Persistence past that point is the behavior people describe as harassment.

**Probe incumbents, never attack them.** Attacking a competitor you can't evidence is weak and it usually reveals you've done no research.

**"Is this a sales call?" deserves a straight answer.** Deflection is both unconvincing and, in several regimes, deceptive practice. Answer, then let them decide.

**A clean exit is a good outcome.** Recording the disposition properly is worth more than squeezing one more turn out of someone who already said no.

---

## Compliance-Linked Objections

These are not sales objections — they're refusals and each requires immediate correct action rather than a response line.

| Signal | Action |
|--------|--------|
| "Stop calling" | Suppress permanently. Apologize. Hang up. |
| "Remove me from your list" | Suppress permanently. Confirm removal. Hang up. |
| Abuse or hostility | Acknowledge once. Hang up. Record disposition. |
| "You're lying about being a bot" | Disclose. Apologize and offer to transfer to a human agent if that is preferable to the callee. If not, exit the conversation politely and hang up. |
| "This is harassment" | Suppress immediately. Do not continue. |

See `../references/outbound-compliance.md`.

---

## Audit Questions

- [ ] Does the agent handle "not the owner" by getting a name or referral?
- [ ] Does it isolate price objections before responding?
- [ ] Does it disclose AI truthfully when asked?
- [ ] Does it re-frame "not interested" exactly once, then exit?
- [ ] Are opt-out phrases routed to suppression, not to a response line?
- [ ] Is there a distinct path for survey calls with no referral ask?
- [ ] Are escalation offers backed by a real destination?
- [ ] Does it avoid arguing with any objection?