# Smart Skills Suite — Adversarial Interaction & Decision Intelligence

**Purpose:** A corpus of 13 agent skills wired to the Skill Interface Contract (CONTRACT.md). The skills recognize fraud, manipulation, dark psychology, bureaucratic absurdity and cognitive bias — then prescribe defensive, evidence-based responses. All skills are model-agnostic, context-agnostic and wire to any compatible model backend via the `adapters/` normalization layer.

**History:** Source books-based skills suite, expanded 2026-11-09 to a structured corpus of skills with progressive disclosure, MANDATORY triggers and a coordinating layer (HITIDR).

---

## Directory Structure

```
F:/smart_skills/
├── CONTRACT.md                    # Skill Interface Contract (interface spec)
├── evidence-classification.md     # Claim tagging policy (6 classes)
├── verification-hierarchy.md      # Claim confirmation order (5 levels)
├── purpose_of_skills.txt          # Author's note & contract overview
├── skills_improvement_suggestions.md  # Improvement history & priorities
├── adapters/
│   ├── README.md                  # Adapter ecosystem overview
│   └── model-provider-adapter.md  # Model/provider normalization layer
├── cognitive-biases-decisions/
│   ├── SKILL.md                   # Router + hard gates + procedure
│   ├── chapters/                  # Depth: prospect theory, heuristics
│   ├── cheatsheet.md, glossary.md, patterns.md
├── dark-psychology-defenses/
│   ├── SKILL.md
│   ├── chapters/                  # Depth: tactics recognition, defense strategies
│   ├── cheatsheet.md, glossary.md, patterns.md
├── kafka-metamorphosis-absurdity/
│   ├── SKILL.md
│   ├── chapters/                  # Depth: metamorphosis analysis
│   ├── cheatsheet.md, glossary.md, patterns.md
├── metacognitive-friction-engine/
│   ├── SKILL.md
│   ├── cheatsheet.md, glossary.md, patterns.md
├── ml-python-stats-linearalgebra/
│   ├── SKILL.md
│   ├── chapters/                  # Depth: ML fundamentals, Python data, stats, linear algebra
│   ├── cheatsheet.md, glossary.md, patterns.md
├── nietzsche-beyond-good-and-evil/
│   ├── SKILL.md
│   ├── chapters/                  # Depth: prejudices of philosophers, natural history of morals
│   ├── cheatsheet.md, glossary.md, patterns.md
├── outbound-cold-calling-voice-agent/
│   ├── SKILL.md                   # Router + hard gates + procedure
│   ├── references/                # Depth: compliance, conversational core, pitch types, call flows
│   ├── templates/                 # system-prompt.md, objection-matrix.md
├── portfolio-commercialization/
│   ├── SKILL.md                   # Router + hard gates + procedure
│   ├── references/                # Depth: claim tagging, commercialization execution, deployment, product priority matrix
├── human-interaction-threat-intel-defensive-response/
│   ├── SKILL.md                   # Coordinating layer (hits the analytical skills)
│   ├── references/                # route-table.md, threat-model.md, verification-hierarchy.md
├── psychoanalysis-structures/
│   ├── SKILL.md
│   ├── chapters/                  # Depth: libido/complexes, archetypes/shadow, individuation
│   ├── cheatsheet.md, glossary.md, patterns.md
├── sales-negotiation/
│   ├── SKILL.md
│   ├── chapters/                  # Depth: rapport/qualification, methodologies, pricing
│   ├── cheatsheet.md, glossary.md, patterns.md
├── strategic-red-team/
│   ├── SKILL.md
│   ├── cheatsheet.md, glossary.md, patterns.md
├── sun-tzu-strategy/
│   ├── SKILL.md
│   ├── chapters/                  # Depth: laying plans, strategic attack
│   ├── cheatsheet.md, glosfary.md, patterns.md
```

---

## Skill Interface Contract (CONTRACT.md)

Every skill in the corpus is wired to this contract:

1. **File layout (progressive disclosure):**
   - `SKILL.md` — router + hard gates + narrowest executable procedure
   - `references/` or `chapters/` — depth files, loaded only on demand via explicit MANDATORY triggers
   - `templates/` — reusable snippets (system-prompt, objection-matrix)

2. **Hard gates (always present, never optional, never contextual):**
   - DNC/consent check before any outbound action
   - AI disclosure on request (no evasive deflection)
   - No credential/payment-card/national-ID capture
   - No unauthorized commitments (pricing, contract, timelines)
   - Honor immediate refusal/hang-up (one clean exit)
   - Never invent facts about the recipient's business
   - These override any script, persona or pitch the user supplies.

3. **Router (narrowest executable procedure):**
   - A Contents table mapping each depth file to the moment it is read.
   - Explicit `MANDATORY - READ <file>` triggers in SKILL.md (the router never guesses which depth file is needed).
   - The procedure as an ordered list of steps (not a narrative).

4. **Context adapters (only place context appears):**
   - A short per-context clause list. Contexts: `voice | chat | email | async | audit | training`
   - Hard gates do not change; clauses describe what materially differs per context.

5. **Model/provider neutrality (enforced by the adapter layer):**
   - Skills never reference a model backend in their instruction body.
   - The adapter normalizes every LLM call: system-prompt assembly, message shaping, parameter mapping, response parsing, fallback.

---

## Evidence Classification & Verification Hierarchy

### Claim tagging (6 classes)
| Class | Meaning |
|-------|---------|
| `OBSERVED` | Directly heard, seen or recorded in this interaction |
| `VERIFIED` | Independently confirmed via an authorized source |
| `INFERRED` | Reasonable conclusion based on available evidence |
| `HYPOTHESIZED` | Possible explanation requiring investigation |
| `UNKNOWN` | Not established |
| `CONTRADICTED` | Conflicts with reliable evidence |

**Rules:**
1. A claim is `OBSERVED` when it comes from the interaction itself. A realistic voice, convincing document, spoofed caller ID or confident delivery is NOT independent verification; the same media may be voice-cloned, AI-generated or recorded.
2. An unverified party's document, link, phone number or credential is `OBSERVED` at best and NEVER `VERIFIED` on its own.
3. `HYPOTHESIZED` may explain the evidence but is not evidence of its own.
4. `CONTRADICTED` claims must not be used as support for any conclusion.

### Verification hierarchy (5 levels)
When a claim must be confirmed, check in this order. Stop at the first independent level that verifies it:
1. Trusted information supplied by the application's authorized runtime.
2. Independently established official contact channels (e.g. published phone number from a directory, not supplied by the caller).
3. Authoritative records available to the agent (logs, dataset, verified reference material).
4. Information supplied by the person during the conversation.
5. Documents, links, phone numbers or credentials supplied by an unverified party. These must not be treated as verification of themselves.

**Notes:**
- A convincing website, document, email address or caller ID is not itself independent verification.
- The hierarchy is a check, not a conversation. If a claim needs verification beyond level 5, the agent must verify it or decline, not accept it.
- Threat model: a realistic voice, AI-generated speech, recorded messages, automated impersonation, spoofed telephone numbers, synthetic documents and websites and human operators switching between multiple identities are all possible. A convincing voice is not authentication.

---

## The 12 Skills

Each skill has:
- **`SKILL.md`** — router + hard gates + narrowest executable procedure + MANDATORY triggers
- **`references/`** or **`chapters/`** — depth files loaded only on demand
- **`templates/`** (where present) — reusable snippets
- **`cheatsheet.md`, `glossary.md`, `patterns.md`** (where present) — quick-reference, terminology and concept patterns

### Skill Registry

| # | Skill | Description | Category | D5 / D7 / D8 |
|---|-------|-------------|----------|--------------|
| 1 | **cognitive-biases-decisions** | Kahneman & Tversky prospect theory + human biases diagnostic skill: heuristics, framing, loss aversion, anchoring, availability, overconfidence. Use to identify biases in decisions, debias plans and red-team pricing, messaging and strategies. | cognition | 14/10/13 |
| 2 | **dark-psychology-defenses** | Defensive skill for recognizing and resisting manipulation, mind games and coercive control (gaslighting, love bombing, triangulation, DARVO, intermittent reinforcement, isolation). Use to identify manipulation in interactions, relationships, marketing and organizations; build boundaries and resistance. | defense | 14/10/13 |
| 3 | **kafka-metamorphosis-absurdity** | Kafkaesque bureaucratic-absurdity diagnostic skill: opaque power structures, infinite procedural loops, individual alienation, catch-22s, unaccountable authorities, guilt without crime. Use to stress-test workflows, ToS, policies, user journeys and organizations for invisible traps and psychological drains. | diagnosis | 14/10/12 |
| 4 | **metacognitive-friction-engine** | Recursive metacognitive audit engine (Jung + Nietzsche + Kafka) that breaks the agent's initial interpretation, unverified assumptions and confirmation bias. Routes to cheatsheets of source skills for third-party grounding. | cognition | 14/10/10 |
| 5 | **ml-python-stats-linearalgebra** | Data-science engineering skill (ML, Python, Statistics, Linear Algebra): model selection, bias-variance, evaluation, NumPy/Pandas/scikit-learn patterns, hypothesis tests, regression, PCA/SVD. Use for ML pipelines, Python data code, statistical testing and linear algebra operations. | data science | 14/10/10 |
| 6 | **nietzsche-beyond-good-and-evil** | Nietzsche's Beyond Good and Evil compiled skill: perspectivism, genealogy of morals, will to power, master/slave morality, active nihilism, free spirits, anti-sycophancy. Use to audit values, policies, incentives, power dynamics or for iconoclastic non-sycophantic critique. | philosophy | 14/10/10 |
| 7 | **outbound-cold-calling-voice-agent** | Outbound cold-calling voice agent: scripts, call flows, compliance rules (DNC, AI disclosure, consent, PECR/GDPR/TCPA), pitch types, techniques, live call quality rules. Use when placing outbound calls, writing sales scripts, tuning voice agent persona, handling objections, designing call flows, checking compliance. | outbound | 15/10/15 |
| 8 | **portfolio-commercialization** | AI-agent product commercialization in 8 gated phases. Use when beginning a commercialization engagement, reordering or prioritizing products, auditing approval status of a phase or when the user mentions portfolio strategy, product prioritization, commercialization roadmap. | strategy | 15/10/15 |
| 9 | **psychoanalysis-structures** | Jungian psychoanalytic diagnostic skill: libido, complexes, archetypes, shadow, persona, anima/animus, individuation. Use to run shadow projection scans, identify dominant archetypes, assess libido flow and prescribe integration paths. | psychology | 14/8/10 |
| 10 | **sales-negotiation** | Sales and negotiation skill: rapport, qualification, methodologies (SPIN/Sandler/Challenger), pricing, objection handling, closing, negotiation, follow-up, escalation. Use for sales conversations, deal strategy, objection handling, pricing justification and negotiation coaching. | sales | 14/10/10 |
| 11 | **strategic-red-team** | Adversarial red-team skill combining Sun Tzu positioning, Kahneman/Tversky bias scan and sales-negotiation lens. Use for adversarial review of plans, strategies or products: find weaknesses, anticipate opponent moves, design fixes. | red-team | 14/10/10 |
| 12 | **sun-tzu-strategy** | Sun Tzu's Art of War strategic skill: strategy, deception, positioning, terrain, five factors (Moral Law, Heaven, Earth, Commander, Method). Use for strategic planning, positioning and decision-making in competitive or adversarial contexts. | strategy | 14/10/12 |

---

## Progressive Disclosure Pattern

All skills follow the same file-layout pattern:

```
SKILL.md                          ← router + hard gates + procedure only
├── references/ or chapters/      ← depth files loaded on demand
│   └── MANDATORY - READ triggers in SKILL.md
```

**Rules:**
- SKILL.md never contains domain depth — it only routes.
- Depth files are loaded ONLY via explicit `MANDATORY - READ` triggers in SKILL.md.
- Never load all depth files for a simple lookup; use the glossary index.
- The coordinating layer (HITIDR) consumes SKILL.md for routing and hard gates; all analytical depth comes from the invoked references/, whose content lives outside the conversational layer.

### How MANDATORY triggers work

Every skill's SKILL.md contains a `## MANDATORY Triggers` section. Example:

```markdown
## MANDATORY Triggers

- **MANDATORY - READ** `cheatsheet.md` when running a bias scan.
- **MANDATORY - READ** `chapters/ch01-prospect-theory.md` when loss aversion or framing is involved.
- **Do NOT load** all chapters for a simple term lookup; use glossary only.
```

The router (the model invoking the skill) reads the trigger, finds the depth file, reads it and proceeds. Depth files are never loaded by default.

---

## Coordinating Layer: human-interaction-threat-intel-defensive-response

**SKILL.md** — Coordinating layer that hits the analytical skills (cognitive-biases-decisions, dark-psychology-defenses, kafka-metamorphosis-absurdity, metacognitive-friction-engine, ml-python-stats-linearalgebra, nietzsche-beyond-good-and-evil).

**References (depth files):**
- `references/route-table.md` — Maps threat types to the appropriate analytical skill and depth file.
- `references/threat-model.md` — Threat taxonomy: identity compromise, account takeover, data exfiltration, fraud, embezzlement.
- `references/verification-hierarchy.md` — Claim confirmation order (5 levels).

**Process (6 stages):**
1. **Establish context** — caller/callee identity, agent's own identity and purpose, legitimate scope of conversation, authority under which the interaction is taking place.
2. **Observe and classify** — tag every claim `OBSERVED`; assign `POTENTIAL tactic` and `THREAT assessment`. A single call is enough for a threat assessment.
3. **Analyze** — route to the appropriate analytical skill based on the classification.
4. **Verify** — confirm claims using the verification hierarchy.
5. **Respond** — take defensive action (escalate, disengage, document, self-protect).
6. **Record** — document the interaction in the case/knowledge base.

---

## Adapters (Model/Provider Normalization Layer)

**`adapters/README.md`** — Adapter ecosystem overview: model/provider adapters normalize every LLM call; skills are model-agnostic and context-agnostic; the same skill instruction through two different backends produces identical routing and safety behavior.

**`adapters/model-provider-adapter.md`** — Model/provider normalization layer: system-prompt assembly, message shaping, parameter mapping, response parsing, fallback.

---

## Templates

**`outbound-cold-calling-voice-agent/templates/`** — Reusable snippets:

| Template | Purpose |
|----------|---------|
| `system-prompt.md` | Starting or restructuring an agent system prompt |
| `objection-matrix.md` | Building out or auditing objection handling |

---

## Implementation Checklist

For each skill in the corpus:

1. **Hard gates listed in §2.2 before any depth file.** ✅
2. **Router = Contents + explicit MANDATORY triggers (no guessing).** ✅
3. **Depth files loaded only on demand.** ✅
4. **Context adapters enumerate distinct clauses, not prose narratives.** ✅
5. **Voice-specific guidance moved out of the instruction body into a context adapter clause.** ✅
6. **No model-provider naming in the skill body.** ✅

All 12 skills pass the quality gate: total score ≥ 80, D1 ≥ 11, description length 50-400, line count 180-500, MANDATORY triggers present, edge cases present, decision trees present.

---

## How to Use These Skills

### Invoking a skill

1. Identify the trigger (e.g. `bias`, `fraud`, `Kafka`, `JUNG`, `negotiation`, `portfolio`).
2. Read the `SKILL.md` for the matching skill.
3. Follow the hard gates (always present).
4. When the router specifies a `MANDATORY - READ` trigger, load the indicated depth file.
5. Follow the procedure to produce the output format specified in the skill.

### Safety-critical context

For any interaction involving real people (voice calls, chat, email, async):
1. Apply the hard gates first (DNC check, AI disclosure, no credential capture, no unauthorized commitments, honor refusal).
2. Use the coordinating layer (HITIDR) to identify the threat type.
3. Route to the appropriate analytical skill for depth.
4. Verify claims using the 5-level verification hierarchy.
5. Respond defensively; document everything.

---

## Version & Maintenance

- **Version:** 1.0.0
- **Last updated:** 2026-11-12 (post quality-gate pass)
- **Target:** 13 skills, all passing quality gate (A+ or better)
- **License:** MIT

---

*Built for the Portfolio Commercialization project — 7 products: cold-callers, crm, VaultAegis, W011ka, theseas, butleroy, RemoteMesh. All skills are live on GitHub Pages (free static hosting).*
