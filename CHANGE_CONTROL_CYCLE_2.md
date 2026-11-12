# Change Control Record — Cycle 2

| Field | Value |
|-------|-------|
| Cycle | 2 (Cycle 1 = contract + adapter layer + voice skill restructure) |
| Date | 2026-11-09 |
| Approved improvement | Adopt a shared evidence-classification and verification-hierarchy convention across all skills |
| Approved proposal | "Evidence & verification discipline" (proposal 2, pre-approved) |
| Result | Implemented and verified |

## Evidence (verification)
- All 13 skill SKILL.md files verified to carry the evidence prerequisite block (grep `Evidence & verification (prerequisite)` on all 13).
- 2 corpus-level references created and confirmed readable.
- Titles preserved for every skill after insertion (no title lost or reordered).

## Files changed
- `cognitive-biases-decisions/SKILL.md`
- `dark-psychology-defenses/SKILL.md`
- `kafka-metamorphosis-absurdity/SKILL.md`
- `metacognitive-friction-engine/SKILL.md`
- `ml-python-stats-linearalgebra/SKILL.md`
- `nietzsche-beyond-good-and-evil/SKILL.md`
- `outbound-cold-calling-voice-agent/SKILL.md`  (renamed from voice-ai-cold-calling-skill)
- `portfolio-commercialization/SKILL.md`
- `psychoanalysis-structures/SKILL.md`
- `sales-negotiation/SKILL.md`
- `strategic-red-team/SKILL.md`
- `sun-tzu-strategy/SKILL.md`
- `test-skill/SKILL.md`
- `evidence-classification.md`  (new, corpus-level shared reference)
- `verification-hierarchy.md`    (new, corpus-level shared reference)
- `adapters/model-provider-adapter.md` (prior cycle)
- `adapters/README.md` (prior cycle)
- `CONTRACT.md` (prior cycle)
- `purpose_of_skills.txt` (prior cycle)

## Files unchanged
- All chapter/reference depth files in existing skill folders.
- `CONTRACT.md` not modified in this cycle (only cross-referenced by the new block).
- `skills_improvement_suggestions.md` (source document; untouched).
- `smart_skills/` is **not a git repository**; no commit performed. Commit when the
  owning GitHub repo (`skills-2026`) is opened for push or via the user's chosen
  version-control step.

## Blocking issue
- Name change: `voice-ai-cold-calling-skill` → `outbound-cold-calling-voice-agent`
  (folder + `name` field in SKILL.md). No source change, purely a rename.

## Verification plan (per proposal)
- Run a test conversation through the corpus; confirm each claim is tagged with the
  correct class and a hypothesis is never promoted to a fact.
- Run the offline harness (existing test suite) on tagged claims.

## Notes/open items
- HITIDR coordination-layer wiring (Stage 4 Verify) is a later cycle and is not yet
  connected to this classification; the shared references are the contract for that
  wiring.
