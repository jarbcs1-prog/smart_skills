# Outbound Cold-Calling Voice Agent — Skill

A skill for building and tuning **AI voice agents that place outbound calls to real humans**. The agent is the caller; the recipient is a person who did not ask to hear from you. Every recommendation here is written from that asymmetry.

## What this skill covers

Outbound call work only:
- **Cold outreach and lead generation**
- **Qualification** of inbound-supplied leads
- **Revival/win-back** of dormant leads and past customers
- **Enrichment** — filling in missing CRM data
- **Surveys, inquiries and investigations**
- **Callbacks and rescheduling**

Inbound reception, IVR routing, social/messaging automation and client retention operations are deliberately out of scope — they dilute the routing an agent does when it needs this skill.

## Structure
```
SKILL.md                             Entry point, non-negotiables, routing
references/
  outbound-compliance.md             DNC, AI disclosure, consent, opt-out  [read first]
  conversational-core.md             Rapport, listening, questions, adapting [always]
  pitch-type-routing.md              Which structure fits which offer type
  call-flows.md                      Six flows as stage machines with gates
  persona-and-pitch-design.md        Entity, persona, pitch, validation
  technique-index.md                 Which technique to load when
  technique-01-research-survey.md    Cold outreach
  technique-02-customer-journey-mirror.md   Post-demo follow-up
  technique-03-revive-and-enrichment.md     Revival + data capture
  technique-04-survey-and-inquiry.md        Research + investigations
  live-call-quality-rules.md         Fourteen rules for every call
  outbound-calling-windows.md        Per-recipient local calling hours
  deployment-gotchas.md              Voice platform wiring traps
  pricing-and-positioning.md         Anchors, ROI, payback, price objections
templates/
  system-prompt.md                   Prompt structure with slot guidance
  objection-matrix.md                Objection coverage + audit
```

## Design principles

**Progressive disclosure.** `SKILL.md` is a router. Depth lives in `references/`, loaded only when the relevant call type comes up.
**Offer-agnostic by construction.** No technique file contains a question, phrase or journey tied to one product. Three-layer split:
- **Mechanics** (`references/conversational-core.md`, quality rules, compliance) — never change per offer
- **Structure** (`references/call-flows.md`, techniques) — change only with the call *type*
- **Content** (pitch records) — the offer lives here

Outbound covers a lot of ground — lead generation, qualification, revival, enrichment, surveys, inquiries, investigations — and each has its own vocabulary. The failure mode of a naive refactor is inheriting one offer's questions into another, so questions are indexed by *purpose* in `technique-01` and selected per `offer_type` rather than hardcoded.

**Compliance as structure, not advice.** The opt-out path, the DNC gate and the AI disclosure are things the agent must *do*, not things a prompt asks it to remember. `references/outbound-compliance.md` is the reference for those controls.

**Config over prose.** Entity facts, persona and pitch content live in records, not prompt text. That makes a campaign change a data edit and it stops the agent contradicting itself about what the business offers.

**Honesty over persuasion.** The techniques that work on a cold call are the ones that survive direct questioning. Deflecting "are you a bot?" loses immediately; disclosing costs less than the complaint it prevents. Manufactured scarcity and false urgency are excluded on compliance grounds, not stylistic ones.

## Using it

Point your agent at `SKILL.md`. The minimum useful set:
1. `references/outbound-compliance.md` — before any run
2. `references/conversational-core.md` — always
3. `references/pitch-type-routing.md` + `references/persona-and-pitch-design.md` — configuring the pitch
4. `references/call-flows.md` — the flow being implemented
5. The matching `references/technique-*.md`
6. `references/live-call-quality-rules.md` — always
7. `templates/system-prompt.md` — when wiring the prompt

## A note on provenance

Techniques 01 and 02 come from Katon Walker's published cold-calling work and are attributed as such. Techniques 03 and 04 are standard outbound practice. Conversational mechanics and the pricing/anchoring model draw on general sales practice — rapport and questioning technique; reference-price anchoring, ROI, payback period and value translation. That source material is written for text-based selling, so voice-specific adaptation notes are included explicitly.

Where the source material advocates tactics that conflict with honest outbound practice — manufactured scarcity, false urgency, fabricated proof — those have been excluded and replaced with their legitimate equivalents. A skill that encourages deceptive practice isn't usable against real recipients.
