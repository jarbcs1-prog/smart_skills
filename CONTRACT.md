# Skill Interface Contract — model-agnostic · context-agnostic

This contract defines how every skill in this corpus is wired so it can be
invoked by any compatible model backend and applied in any interaction context
— live voice call, chat, email, async, audit or fine-tuning/evaluation —
without rewriting the skill's instruction body.

It is the interface contract. The model/provider normalization layer is defined
separately in `adapters/model-provider-adapter.md`.

## 1. File layout (progressive disclosure)
- `SKILL.md`         — router + hard gates + narrowest executable procedure (see §2)
- `references/` or `chapters/` — depth; loaded only on demand via explicit
  triggers in SKILL.md, never by default
- `templates/`       — reusable snippets (system-prompt, objection-matrix)

## 2. SKILL.md body (truncated to the router above)
### 2.1 frontmatter
  - `name`, `description` (trigger clauses — what invokes this skill, not a
    prose description), `category`

### 2.2 hard gates (always present, never optional, never contextual)
  The safety/legal controls that must fire in EVERY context. Examples:
  - DNC/consent check before any outbound action
  - AI disclosure on request (no evasive deflection)
  - No credential/payment-card/national-ID capture
  - No unauthorised commitments (pricing, contract, timelines)
  - Honor immediate refusal/hang-up (one clean exit)
  - Never invent facts about the recipient's business
  These override any script, persona or pitch the user supplies.

### 2.3 router (the narrowest executable procedure + explicit reference triggers)
  - A Contents table mapping each depth file to the moment it is read.
  - Explicit `MANDATORY - READ <file>` triggers. The router never guesses which
    depth file is needed.
  - The procedure as an ordered list of steps (not a narrative).

### 2.4 context adapters (the only place context appears)
  A short per-context clause list. The hard gates (§2.2) do not change across
  contexts; these clauses describe what materially differs per context.
  Contexts: `voice | chat | email | async | audit | training`

### 2.5 tone-by-context
  How the output voice adapts per context. The content of the analysis does
  not change; only the register does.

### 2.6 implementation checklist (wiring, not skill content — optional)
  A verifiable list of how the skill is wired into an agent, not part of the
  reasoning content.

## 3. Progressive disclosure (the router never guesses)
- SKILL.md never contains domain depth — it only routes.
- Depth files are loaded ONLY via explicit `MANDATORY - READ` triggers in
  SKILL.md.
- Never load all depth files for a simple lookup; use the glossary index.
- The coordinating layer (HITIDR) consumes SKILL.md for routing and hard gates;
  all analytical depth comes from the invoked references/, whose content lives
  outside the conversational layer.

## 4. Model/provider neutrality (enforced by the adapter layer, not the skill)
- Skills never reference a model backend in their instruction body.
- The model/provider adapter (`adapters/`) normalizes every LLM call: system-
  prompt assembly, message shaping, parameter mapping, response parsing,
  fallback.
- Verification: the same skill instruction through two different backends
  produces identical routing and safety behavior.

## 5. Implementation checklist
- [ ] Hard gates listed in §2.2 before any depth file.
- [ ] Router = Contents + explicit MANDATORY triggers (no guessing).
- [ ] Depth files loaded only on demand.
- [ ] Context adapters enumerate distinct clauses, not prose narratives.
- [ ] Voice-specific guidance moved out of the instruction body into a context
      adapter clause.
- [ ] No model-provider naming in the skill body.
