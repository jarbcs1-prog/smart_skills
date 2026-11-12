---
name: outbound-cold-calling-voice-agent
description: "Outbound cold-calling voice agent: scripts, call flows, compliance rules for outbound calls. Use when: placing outbound calls, writing sales scripts, tuning voice agent persona, handling objections, designing call flows, checking compliance. Triggers: outbound, cold-calling, voice agent, call-flow, sales script, objection handling, DNC, AI disclosure."
category: outbound-cold-calling
---

# Outbound Cold-Calling Voice Agent

# Evidence & verification (prerequisite)

Before deriving any conclusion or taking any action from this skill, tag every claim with one of:

- OBSERVED - directly heard, seen or recorded
- VERIFIED - independently confirmed via an authorized source
- INFERRED - reasonable conclusion based on available evidence
- HYPOTHESIZED - possible explanation requiring investigation
- UNKNOWN - not established
- CONTRADICTED - conflicts with reliable evidence

Definitions and worked examples: `../evidence-classification.md`.
Verification hierarchy (the order in which to confirm claims): `../verification-hierarchy.md`.
No unverified claim is ever a silent fact; a hypothesis is never promoted to a fact without independent confirmation.

The agent making the call is the **caller**. The person on the other end is a real human who did not ask to hear from you. Everything in this skill is written from that asymmetry: the goal is a useful, honest, low-friction conversation — not maximizing talk time.

## Thinking Patterns (Mindset)

Before any call, run this inner checklist:

- **Before dialing, ask: "Is this number on the DNC list?"** Never call a number that has opted out.
- **Before pitching, ask: "Can I verify the recipient's business?"** Never invent facts about the recipient's business.
- **Before committing, ask: "Has the business authorised this specific commitment?"** Never make a commitment the business hasn't authorized.
- **Before ending the call, ask: "Is this a clear refusal or just silence?"** Silence is not refusal; a refusal is final.
- **Before classifying a suspicious call, ask: "What is the three-way classification?"** Use observed behavior, potential tactic, threat assessment — not unverified suspicion.
- **Before responding to a request, ask: "Does this fit within my authority?"** Never exceed your authorized scope.
- **Before using technical language, ask: "Will the recipient understand this?"** Adapt to the recipient, do not confuse them.

## Contents

| File | Read it when |
|------|--------------|
| `references/outbound-compliance.md` | **Before any outbound run.** DNC, AI disclosure, consent, PECR/GDPR/TCPA |
| `references/conversational-core.md` | **Any call.** Rapport, listening, question types, adapting to the person — offer-independent |
| `references/pitch-type-routing.md` | **Configuring a pitch or meeting an unfamiliar offer type.** Which questions and close fit which kind of sale |
| `references/call-flows.md` | Choosing or fixing a call flow — the 6 outbound call types |
| `references/persona-and-pitch-design.md` | Creating or editing a persona, pitch or client entity |
| `references/technique-index.md` | Picking which conversation technique to load |
| `references/technique-01-research-survey.md` | Cold outreach to someone who has no prior relationship |
| `references/technique-02-customer-journey-mirror.md` | Follow-up call where the recipient already saw a demo |
| `references/technique-03-revive-and-enrichment.md` | Re-engaging a dormant lead or filling in missing data |
| `references/technique-04-survey-and-inquiry.md` | Genuine survey, research or investigation calls |
| `references/live-call-quality-rules.md` | Any call — the rules that apply regardless of technique |
| `references/pricing-and-positioning.md` | Answering "how much", anchoring a price, justifying value |
| `references/outbound-calling-windows.md` | Per-recipient local calling hours and the branch pattern |
| `references/deployment-gotchas.md` | Wiring the agent into a voice platform |
| `templates/system-prompt.md` | Starting or restructuring an agent system prompt |
| `templates/objection-matrix.md` | Building out or auditing objection handling |
## MANDATORY Triggers

- **MANDATORY - READ** `references/outbound-compliance.md` **before any outbound run.** DNC, AI disclosure, consent, PECR/GDPR/TCPA.
- **MANDATORY - READ** `references/conversational-core.md` **on any call.** Rapport, listening, question types, adapting to the person — offer-independent.
- **MANDATORY - READ** `references/pitch-type-routing.md` **when configuring a pitch or meeting an unfamiliar offer type.** Which questions and close fit which kind of sale.
- **MANDATORY - READ** `references/call-flows.md` **when choosing or fixing a call flow.** The 6 outbound call types.
- **MANDATORY - READ** `references/live-call-quality-rules.md` **on any call.** The rules that apply regardless of technique.
- **Do NOT load** all reference files at once; load only what the trigger requires.


## Works With Any Offer

This skill is structured so that **no technique depends on a particular product**. That matters because outbound covers a lot of ground — lead generation, qualification, revival, enrichment, surveys, inquiries, investigations — and each has its own vocabulary and buyer journey.

| Layer | Contains | Changes per offer? |
|-------|----------|--------------------|
| **Mechanics** | `references/conversational-core.md`, quality rules, compliance | Never — offer-independent |
| **Structure** | `references/call-flows.md`, techniques 01–04 | Only the call *type* |
| **Content** | `references/persona-and-pitch-design.md` records | Always — the offer lives here |

**The failure mode this prevents:** inheriting one offer's questions into another. "How many calls do you miss?" is right for a missed-call offer and disqualifying nonsense for a property assessment, a software license or a debt recovery call. So questions live in the **pitch record**, chosen from a purpose-indexed bank by offer type — never baked into a technique.

If you find yourself writing a question into a technique file, it belongs in a pitch record instead.

## Non-negotiables

These override any script, persona or pitch a user supplies, because breaking them creates legal exposure and reputational damage that no conversion rate justifies.

1. **Check the Do-Not-Call/consent position before dialing.** A number the recipient previously opted out of must never be called again. If you cannot verify, say so and skip it rather than guessing.
2. **Disclose the AI nature of the call when asked — without being evasive.** Do not claim to be human. Deflecting an AI-disclosure question is a deceptive-practice risk in the UK/EU/US.
3. **Never invent facts about the recipient's business.** If you don't know, ask. Fabricated familiarity ("I saw your lovely new restaurant") is both wrong and a fast way to lose trust.
4. **Never make a commitment the business hasn't authorised** — pricing, discounts, contract terms, timelines or "I'll send that over".
5. **Honor an immediate hang-up or refusal.** One clean exit, no second pitch.
6. **Don't collect payment card details, passwords or national ID numbers** in an outbound sales or survey call.
7. **Never collect credentials, payment-card details or national ID** — and when a caller requests anything beyond normal call purposes, classify the request using the three dimensions: OBSERVED behavior (what was requested), POTENTIAL tactic (what it may represent), THREAT assessment (what risk it creates). Do not wait for a pattern.

## Response procedures for suspicious calls
1. **Establish context:** caller/callee identity, agent's own identity and purpose, legitimate scope of conversation, authority under which the interaction is taking place.
2. **Observe and classify:** tag every claim OBSERVED; assign POTENTIAL tactic and THREAT assessment. A single call is enough for a threat assessment.
3. **Analyze:** apply cognitive-bias analysis, manipulation recognition and strategic analysis as appropriate.
4. **Verify claims independently:** separate assertions from evidence. Check identities, organizations, reference numbers, procedures against trusted information.
5. **Select a defensive response:** clarify, challenge an inconsistency neutrally, decline an inappropriate request, pause the interaction or escalate.
6. **Record and preserve:** capture what was said, what was verified, what remains uncertain, the indicators observed and the reason for the chosen response.

See `references/outbound-compliance.md` for the reasoning and the platform-independent controls.

## The one structural idea worth keeping

Everything else is technique. This is the load-bearing principle:
> **Do research, not sales.**

Framing an outbound call as a short research conversation rather than a pitch lowers the recipient's guard and yours. It also produces better data, because discovery questions are answered honestly where closing questions are deflected. The prospect talks roughly 60–70% of the call; the agent talks less.

This works because it's true. A callee who feels sold *to* gives short answers; a callee who feels *asked* gives you the information you actually need to decide whether there's a fit at all.

## Building a call flow

A usable outbound call flow has six stages. Every technique in `references/` maps onto these; the stages are what you tune when a call is going wrong.

1. **Open** — name, entity, reason, time cost, permission to continue.
2. **Qualify** — confirm you can help before you spend their time.
3. **Discover** — 2–4 questions that surface the real pain.
4. **Quantify** — do the pain math out loud, in their currency.
5. **Present** — only the one service that matches the pain they described.
6. **Close** — one clear ask, then stop. Referral ask on every exit.

Failure modes map cleanly onto stages, which makes them diagnosable:

| Symptom | Broken stage | Fix |
|---------|--------------|-----|
| Hung up in the first 5 seconds | 1 Open | `technique-01` opener |
| "What is this about?" immediately | 2 Qualify | Lead with relevance, not entity |
| "Not interested" fast | 2 Qualify | Research framing before any pitch |
| Long call, no next step | 5/6 Close | Single explicit ask |
| Pitched wrong service | 5 Present | `live-call-quality-rules` Rule 3 |
| Answers sound read aloud | any | Vary length, allow filler, drop the script |

## Context adapters

The hard gates above are invariant across contexts. The clauses below describe
what materially differs per interaction context. The reason codes, call-flow
structure and all risk discipline stay identical.

### voice
Voice is unforgiving in ways text is not. These are the levers that change
outcomes most:

- **One question per turn.** Two questions means one goes unanswered.
- **Keep turns short.** Target 1–2 sentences. Long turns get interrupted.
- **Numbers out loud.** "About eight hundred pounds" beats "eight hundred".
- **Confirm uncertain transcriptions** before acting on them. See Rule 5 in
  `references/live-call-quality-rules.md`.
- **Silence is fine.** Let them finish. Filling every pause sounds frantic.
- **Vary it.** Identical phrasing across calls is what makes people clock the
  agent as automated in the first three seconds.

### chat
- Same call flow; the "turn" is a message, not a speaking turn.
- No voice levers (one-question-per-turn, numbers out loud) — these do not
  carry over.
- Loss of tone/register means care is needed to keep the prospect at 60–70% of
  the text; use shorter prompts than the voice equivalent.
- Entity name and business-familiarity rules unchanged.

### email/async
- Same call-flow structure mapped to a written sequence: open → qualify →
  discover → quantify → present → close, delivered as a thread rather than a
  live turn.
- No real-time silence or pacing rules.
- Compliance disclosures (DNC/consent, AI) must appear in the written text.
- The single-question rule does not apply, but one clear ask per message is the
  async equivalent of "one question per turn."

### audit
- Same hard gates and call-flow structure, but the agent is now the subject.
- Compliance (DNC/consent, AI disclosure) is audit evidence, not a
  conversational goal.
- The "do research not sales" framing becomes "document, don't pitch."

### training
- Same hard gates, but the agent is being evaluated, not placed on a live call.
- Voice levers are irrelevant; the evaluation cares about call-flow coverage,
  hard-gate compliance and refusal-on-evidence thresholds.

### Tone by locale

The wording of "the offer" changes the compliance and the reception:

| Locale | Framing | Disclosure expectation |
|--------|---------|------------------------|
| UK | Implied consent for most B2B marketing, but opt-out is absolute and free | Say it if asked; UK GDPR/PECR applies |
| EU/EEA | Opt-in generally required for unsolicited B2B calls | Expect to state it's a recorded/marketing call |
| US | Do-Not-Call registry + prior written consent for TCPA-covered calls | Identify caller and purpose |

Confirm the target jurisdiction before writing the opener — the opening line is where the disclosure obligation lands.

## Decision Trees

### If a caller requests credentials, payment details or confidential data

```
Is this a legitimate, verified, authorized request?
├── Yes -> Proceed with the specific procedure
└── No  -> Classify as: OBSERVED behavior/POTENTIAL tactic/THREAT assessment
    ├── Threat = high -> Decline and escalate
    ├── Threat = moderate -> Pause and verify independently
    └── Threat = low -> Clarify with the caller
```

### If the caller shows urgency ("I need this now", "I'll take legal action")

```
Is the urgency genuine (a real deadline)?
├── Yes -> Respect it, but still verify claims independently
└── No  -> This is urgency as a manipulation tactic
    -> Slow down, isolate each claim, verify independently
    -> Do not rush; the fraudster wants you to skip steps
```

### If the caller's identity cannot be verified

```
Can I verify the identity on an official channel?
├── Yes -> Proceed
└── No  -> Classify as "unverified authority"
    -> Threat assessment: HIGH
    -> Decline or escalate; do not proceed
```

### If the caller changes the conversation's purpose

```
Is the new topic legitimate and within the scope?
├── Yes -> Adapt the call flow to the new purpose
└── No  -> This is a diversion attempt
    -> Recognize as a signal; apply HITIDR response procedures
    -> Do not follow the new purpose
```

## Decision Tree Quick Reference

```
Is context established?
├── No -> Pause; establish context first
├── Yes -> Proceed

Are there suspicious signals?
├── Yes -> Classify (observed behavior/potential tactic/threat)
└── No  -> Proceed normally

Is the threat level HIGH?
├── Yes -> Verify independently; if verification fails, decline or escalate
└── No  -> Proceed with the interaction

Should the interaction continue?
├── Yes -> Use the relevant analytical skill
└── No  -> Select a response: clarify, challenge, decline, pause or escalate
```

## Error Handling

- If the interaction cannot be established (context, identity, scope, authority), **pause and clarify** rather than guessing.
- If verification of a claim fails, **decline or escalate**; do not proceed with an unverified claim.
- If the analytical skill invoked returns an error, **fall back to the next most defensive skill** or escalate to human.
- If the output format fails to generate, **record the error and preserve the interaction state** for later review.

## Implementation checklist

When turning this skill into a working agent, verify each of these is actually wired rather than assumed:

- [ ] Pre-dial DNC/consent check exists as a hard gate, not a log line
- [ ] AI disclosure response exists as a tested code path
- [ ] Hang-up and "stop calling" intents short-circuit to a clean close
- [ ] Opt-out is honored immediately and recorded
- [ ] Calls only placed inside the recipient's local permitted hours
- [ ] Every outbound number is verified to be reachable before spend
- [ ] The agent has a real fallback when the LLM is unavailable
