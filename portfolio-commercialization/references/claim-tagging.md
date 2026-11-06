# Claim tagging reference

Every claim in portfolio deliverables is tagged VERIFIED/INFERRED/ASSUMED/UNKNOWN. Apply the tag to the claim itself, not to the document as a whole.

## Definitions

| Tag | Meaning |
|-----|---------|
| VERIFIED | Supported by source evidence observed in this session (read files, ran commands, inspected output). |
| INFERRED | Corroborated by evidence in this session but not directly observed (e.g. behavior deduced from code + docs). |
| ASSUMED | Conventional hypothesis. Not yet validated with live buyers. |
| UNKNOWN | Not yet determined or not yet verified. |

## Usage rules
- Tag the claim, not the section. Example: "The product is local-first, but the web-research skills send queries to DuckDuckGo (VERIFIED)". |
- Repeating a verified claim does not require re-tagging, but a new claim does.
- Mark the pricing/tiers as ASSUMED until WTP is validated with live buyers.
- When uncertain, default to INFERRED or ASSUMED rather than claiming more than the evidence supports.

## Examples from this portfolio
- "The product is local-first (VERIFIED from README: Ollama, LM Studio, KoboldCPP, LlamaCPP support)." |
- "Web-research skills send queries to DuckDuckGo (VERIFIED; DuckDuckGo-only in README)." |
- "The data-boundary rules are prompt-level (advisory), not hard code-level (INFERRED from README + CHANGES)." |
- "A specific SKU is too cheap to cover CAC (ASSUMED; no WTP data yet)." |
- "Enterprise SSO and audit-grade compliance (UNKNOWN until docs/SECURITY.md and architecture review are completed)."

## Related
- SKILL.md standing rules: all claims tagged VERIFIED/INFERRED/ASSUMED/UNKNOWN.