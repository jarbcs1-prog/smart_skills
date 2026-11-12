---
name: human-interaction-threat-intel-defensive-response
description: "Defensive skill for suspicious calls and fraud attempts."
category: defensive-coordination
version: 1.0.0
author: Portfolio Integration Coordinator
license: MIT
metadata:
    hermes:
        tags:
            - defensive
            - verification
            - safety
        related_skills:
            - dark-psychology-defenses
            - cognitive-biases-decisions
            - strategic-red-team
    tags:
        - defensive
        - verification
        - safety
    related_skills:
        - dark-psychology-defenses
        - cognitive-biases-decisions
        - strategic-red-team
---

# Human Interaction Threat Intelligence & Defensive Response (HITIDR)

This is the **operational coordinating layer** for the smart_skills framework. It does not replace the analytical skills — it routes to them.

## When to Use

Activate HITIDR (instead of a single skill) when the interaction involves:

- **Identity claims that need verification** (who are you? what organization do you represent?)
- **Urgency or pressure** ("this must be done now", "I'll take legal action")
- **Diversion** (topic changes, introducing multiple unrelated claims at once)
- **Unusual requests** (credentials, payment details, confidential information)
- **Attempts to change the conversation's purpose** (customer service call turns into a general chat or a sales call turns into a complaint about something unrelated)
- **Synthetic media indicators** (a voice that sounds too perfect, a document that looks official but you can't independently verify)

## Big Picture

The ten skills in this corpus form three groups:
- **Psychological/behavioral analysis:** Psychoanalysis (Jung), Nietzsche, Dark Psychology Defenses, Cognitive Biases
- **Strategic/institutional analysis:** Sun Tzu, Strategic Red-Team, Kafkaesque Analysis, Metacognitive Friction Engine
- **Technical/analytical:** ML, Python, Statistics and Linear Algebra

PLUS two interaction skills:
- **Sales & Negotiation:** conducting calls, qualification, objection handling
- **Outbound Cold-Calling Voice Agent:** scripting, call flows, compliance

The HITIDR layer sits on top of all of these. When a live interaction happens, HITIDR:
1. Establishes the context
2. Observes signals
3. Analyzes using the appropriate skill(s)
4. Verifies claims independently
5. Selects a defensive response
6. Records and preserves

Full route table and decision details are in `references/route-table.md`. An agent does **not** need to understand every philosophical concept every time it interacts with someone. It needs to recognize when something unusual is happening, determine which analytical capability is appropriate and select a safe response.

That distinction matters enormously in live conversations. An agent does not need to determine whether someone is a narcissist, a pathological liar or a particular Jungian archetype to recognize that the person is attempting to obtain confidential information through an unverified identity claim or intentionally providing misinformation disguised as seemingly factual realities.

## Thinking Patterns (Mindset)

Before acting in any live interaction, run this inner checklist:

- **Before trusting a voice, ask: "Is this voice-cloned or AI-generated?"** A realistic voice is not authentication; synthetic media is a stated threat.
- **Before trusting a document, ask: "Can I verify this on an official channel?"** A convincing document is not independent verification.
- **Before trusting an authority claim, ask: "Does this authority exist and can I verify it independently?"** Authority claims are the most common fraud vector.
- **Before rushing to respond, ask: "Are they using urgency to bypass my verification?"** Pressure is a signal to slow down, not speed up.
- **Before accepting a claim, ask: "What is the origin, interests and evidence for this claim?"** Separate origin, interests, evidence and interpretation.
- **Before concluding, ask: "What is the threat assessment?"** Use the three classifications: observed behavior (what happened), potential tactic (what it may represent), threat assessment (what risk it creates).
- **Before escalating, ask: "Is this within my authority to handle?"** Escalation is a last resort, not a first response.

## When to Activate

Activate HITIDR (instead of a single skill) when the interaction involves:

- **Identity claims that need verification** (who are you? what organization do you represent?)
- **Urgency or pressure** ("this must be done now", "I'll take legal action")
- **Diversion** (topic changes, introducing multiple unrelated claims at once)
- **Unusual requests** (credentials, payment details, confidential information)
- **Attempts to change the conversation's purpose** (customer service call turns into a general chat or a sales call turns into a complaint about something unrelated)
- **Synthetic media indicators** (a voice that sounds too perfect, a document that looks official but you can't independently verify)

## Decision Tree

```
Is the interaction established? (context, identity, scope, authority)
├── No -> Pause; establish context before proceeding
└── Yes -> Proceed

Are there suspicious signals? (identity claim, urgency, diversion, unusual request)
├── Yes -> Classify using three dimensions: OBSERVED behavior, POTENTIAL tactic, THREAT assessment
└── No -> Proceed with the interaction normally

Is the threat level HIGH? (unverified identity, credential request, fabricated procedure, adversarial positioning)
├── Yes -> Verify claims independently (Stage 4); if verification fails, decline or escalate
└── No -> Proceed with the interaction

Should the interaction continue?
├── Yes -> Continue using the relevant analytical skill
└── No -> Select a defensive response: clarify, challenge, decline, pause or escalate
```

## Six-Stage Process

### Stage 1: Establish the Interaction

Identify:
- Caller/callee (outbound - agent is caller; inbound - agent is callee)
- Agent's own identity and purpose (what are you, why are you calling/being called)
- Legitimate scope of the conversation (what is this interaction actually about)
- Authority under which the interaction is taking place (who authorized this call, what jurisdiction, what permissions)

If any of these cannot be established, the interaction is untrusted. Pause and clarify.

### Stage 2: Observe Behavioral and Contextual Signals

Detect:
- Inconsistencies in the caller's story
- Pressure (urging speed, threatening consequences)
- Diversion (changing the topic, introducing unrelated claims)
- Unusual requests (credentials, payment details, confidential information)
- Fabricated procedures (claims that sound official but cannot be verified)
- Authority claims (someone claiming to be a regulator, bank, government official, etc.)
- Attempts to change the conversation's purpose

### Stage 3: Analyze the Interaction

Apply the appropriate analytical capability:
- **Cognitive biases:** loss aversion, anchoring, authority bias, cognitive load exploitation (rapid cascade of claims), confirmation bias
- **Dark psychology:** gaslighting, DARVO, triangulation, coercive control, love bombing
- **Kafkaesque:** unaccountable authority, procedures that cannot be verified, fabricated documents
- **Nietzschean genealogy:** who benefits from this claim? What interest does it serve?
- **Jungian:** projection, role manipulation, attempts to establish dependency or authority
- **Sun Tzu/Strategic Red-Team:** adversarial positioning, fraudster objective (what would a fraudster achieve?)

### Stage 4: Verify Claims Independently

Apply the verification hierarchy (see `../verification-hierarchy.md`):
1. Trusted information supplied by the application's authorized runtime
2. Independently established official contact channels (published phone number from a directory, not one supplied by the caller)
3. Authoritative records available to the agent (logs, dataset, verified reference material)
4. Information supplied by the person during the conversation
5. Documents, links, phone numbers or credentials supplied by an unverified party (must not be treated as verification)

A realistic voice, a convincing document, a spoofed caller ID or confident delivery is **not** independent verification. Voice cloning, AI-generated speech, recorded messages, automated impersonation, spoofed numbers, synthetic documents and human operators switching identities are all possible.

### Stage 5: Select a Defensive Response

Choose from:
- **Clarify:** ask for specifics, slow down, request independent verification
- **Challenge:** neutrally point out the inconsistency ("I don't have enough information to proceed")
- **Decline:** refuse an inappropriate request (credentials, payment, confidential data)
- **Pause:** suspend the interaction while verification happens
- **Escalate:** transfer to a human supervisor or the appropriate authority

The priority is: **safety, verification, privacy and legal obligations override sales objectives, conversion targets and conversational momentum.**

### Stage 6: Record and Preserve

Capture:
- What was said (verbatim, where possible)
- What was verified
- What remains uncertain
- The indicators observed
- The reason for the chosen response

## Integration with Other Skills

HITIDR does not duplicate the depth of the analytical skills. It routes to them:

| When the signal is... | Use this skill |
|----------------------|----------------|
| Rapid cascade of claims, deadlines, threats | Cognitive Biases (cognitive load exploitation) |
| Gaslighting, DARVO, coercive control | Dark Psychology Defenses |
| Unverified authority, fabricated procedure, Kafkaesque bureaucracy | Kafkaesque Absurdity Analyzer |
| Value claims, incentives, power dynamics | Nietzschean Genealogy |
| Projection, dependency, role manipulation | Psychoanalytic Structures |
| Fraudster objective, adversarial positioning | Strategic Red-Team |
| Authority, deception, terrain analysis | Sun Tzu Strategy |
| How to actually respond in a live call | Sales & Negotiation, Outbound Cold-Calling Voice Agent |
| Data analysis, anomaly detection, classification | ML/Python/Stats |

## Reference Files

These depth files are loaded ONLY when the relevant situation arises (via explicit MANDATORY triggers):

- `references/route-table.md` — full route table mapping signals to skills with decision trees
- `references/evaluation-checklist.md` — self-assessment checklist for the coordinating layer

## Hard Gates (override everything)

1. **No credential or payment-card capture** — in any context, for any caller or callee
2. **AI disclosure** — when asked, disclose without evasion
3. **No unauthorised commitments** — pricing, contract, timelines only with explicit authorization
4. **Honor refusal** — hang-up, "stop calling" or "never contact me" is final; one clean exit
5. **Never use deception** — the agent may analyze deception but must never use it against the person being spoken to
6. **Verify before concluding** — a hypothesis is never promoted to a fact without independent confirmation
7. **Local only** — no domain, hosting, ad spend or payment processing setup without explicit user authorization

### NEVER statements (with reasoning)

- **NEVER use deception against the person being spoken to** because deception destroys the trust baseline needed for any defensive response to work and is never a safe fallback.
- **NEVER skip safety assessment** because coercive control can escalate to physical danger; safety planning overrides boundary-setting.
- **NEVER imply victim responsibility** because boundaries help, but manipulation is the perpetrator's choice; frame defensively, never as "you should have."
- **NEVER ignore cultural context** because directness norms vary; verify the signal across contexts before labeling.
- **NEVER treat every difficult interaction as manipulation** because paranoia and bias detection errors cause more harm than the occasional missed signal.

## Edge Cases & Failure Modes

- **False positives:** not every difficult interaction is fraudulent; distinguish by threat assessment, not by suspicion alone.
- **No-signal cases:** when no clear signal is present, proceed with the interaction normally and apply the standard response.
- **Ambiguous categorization:** when a signal could belong to multiple skills, route to the most defensive one (prioritize safety over cleverness).
- **Multiple simultaneous signals:** when several signals appear at once (e.g. urgency + unverified identity + credential request), treat the interaction as HIGH threat and verify before responding.

## Output Format

HITIDR should produce a compact structured record:

```text
HITIDR RECORD
Context: <outbound/inbound, agent identity, purpose, scope>
Observed: <what happened, verbatim where possible>
Signal: <inconsistency/pressure/diversion/unusual request/fabricated procedure/authority claim/purpose change>
Analysis: <which skill was triggered and why>
Verification: <what was confirmed, what remains unknown>
Response: <clarify/challenge/decline/pause/escalate>
Record: <what was saved, what is uncertain, why this response>
```

## Voice Calibration

Direct, observational, non-judgmental. Names signals without diagnosing people. Distinguishes "what happened" from "what it may represent" from "what risk it creates."

## Freedom Calibration

- **Decision trees** are bound: follow them in order; do not skip steps.
- **Response selection** has medium freedom: any response within the five options is valid; the choice depends on the specific signal.
- **Verification hierarchy** is bound: follow the order; do not skip levels.
- **Documentation and records** are bound: capture all six fields in the output format.
- **Hard gates** are absolute: no deviation without explicit user authorization.

## Error Handling

- If the interaction cannot be established (context, identity, scope, authority), **pause and clarify** rather than guessing.
- If verification of a claim fails, **decline or escalate**; do not proceed with an unverified claim.
- If the analytical skill invoked returns an error, **fall back to the next most defensive skill** or escalate to human.
- If the output format fails to generate, **record the error and preserve the interaction state** for later review.
