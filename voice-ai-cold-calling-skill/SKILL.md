---
name: outbound-cold-calling-voice-agent
description: >-
  Scripts, call flows, personas and compliance rules for AI voice agents that place
  OUTBOUND calls to real human recipients. Covers cold outreach and lead generation,
  qualification calls, revival/win-back calls, list enrichment calls, surveys,
  inquiries and investigations — plus objection handling, pain-math framing,
  persona and pitch design, AI-disclosure and Do-Not-Call obligations and prompt
  templates. Use this skill whenever the task involves placing outbound calls,
  writing or reviewing a cold-calling or sales-call script, tuning a voice agent's
  persona, handling objections or gatekeepers, designing call flows or checking
  outbound calling compliance — even if the user only says "write a script", "fix
  my opener", "the agent sounds robotic", "why do they hang up", "add a persona"
  or "what should it say when they say no". Trigger it for any telephony prompt,
  call-flow or sales-call QA work; it is not needed for purely inbound receptionist
  or IVR routing tasks.
---

# Outbound Cold-Calling Voice Agent

The agent making the call is the **caller**. The person on the other end is a real human who did not ask to hear from you. Everything in this skill is written from that asymmetry: the goal is a useful, honest, low-friction conversation — not maximizing talk time.

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

## Voice-specific guidance

Voice is unforgiving in ways text is not. These are the levers that change outcomes most:

- **One question per turn.** Two questions means one goes unanswered.
- **Keep turns short.** Target 1–2 sentences. Long turns get interrupted.
- **Numbers out loud.** "About eight hundred pounds" beats "eight hundred".
- **Confirm uncertain transcriptions** before acting on them. See Rule 5 in `references/live-call-quality-rules.md`.
- **Silence is fine.** Let them finish. Filling every pause sounds frantic.
- **Vary it.** Identical phrasing across calls is what makes people clock the agent as automated in the first three seconds.

## Tone by locale

The wording of "the offer" changes the compliance and the reception:

| Locale | Framing | Disclosure expectation |
|--------|---------|------------------------|
| UK | Implied consent for most B2B marketing, but opt-out is absolute and free | Say it if asked; UK GDPR/PECR applies |
| EU/EEA | Opt-in generally required for unsolicited B2B calls | Expect to state it's a recorded/marketing call |
| US | Do-Not-Call registry + prior written consent for TCPA-covered calls | Identify caller and purpose |

Confirm the target jurisdiction before writing the opener — the opening line is where the disclosure obligation lands.

## Implementation checklist

When turning this skill into a working agent, verify each of these is actually wired rather than assumed:

- [ ] Pre-dial DNC/consent check exists as a hard gate, not a log line
- [ ] AI disclosure response exists as a tested code path
- [ ] Hang-up and "stop calling" intents short-circuit to a clean close
- [ ] Opt-out is honored immediately and recorded
- [ ] Calls only placed inside the recipient's local permitted hours
- [ ] Every outbound number is verified to be reachable before spend
- [ ] The agent has a real fallback when the LLM is unavailable
