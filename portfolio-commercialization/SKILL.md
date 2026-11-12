---
name: portfolio-commercialization
description: "AI-agent product commercialization in 8 gated phases. Use when: beginning a commercialization engagement, reordering or prioritizing products, auditing approval status of a phase or when the user mentions portfolio strategy, product prioritization, commercialization roadmap. Triggers: portfolio, commercialization, product prioritization, commercialization roadmap, 8-phase, approval gates."
category: portfolio
version: 1.0.0
author: jarbcs1-prog
license: MIT
metadata:
    tags:
      - portfolio
      - commercialization
    related_skills:
      - product-manager
      - business-strategist
---

# Portfolio Commercialization

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

Class-level skill for systematic commercialization of software products portfolio by AI agents through an 8-phase sequence with staged approval gates, read-only discovery, claim tagging and per-product milestone execution.

## When to use
- Beginning any portfolio commercialization engagement
- Re-ordering or re-prioritizing products in existing portfolios
- Auditing whether a phase or action is approved or still gated

## Thinking Patterns (Mindset)

Before any portfolio commercialization action, run this inner checklist:

- **Before entering a phase, ask: "Is the previous phase's deliverable approved?"** Do not skip approval gates.
- **Before designing a commercialization strategy, ask: "What is the smallest viable commercial experiment?"** Start small; expand only after validation.
- **Before committing to a product priority, ask: "What is the evidence for this ranking?"** Scores must be traceable to verified data.
- **Before authorizing expenditure, ask: "What is the minimum spend that tests the hypothesis?"** Avoid over-spending before validation.
- **Before declaring a phase complete, ask: "Are all deliverables verified and approved?"** No phase may pass a gate without verified deliverables.
- **Before escalating an issue, ask: "Is this within my authority to resolve?"** Escalate only when necessary.
- **Before reporting portfolio status, ask: "What is the evidence for this claim?"** Tag every claim: VERIFIED/INFERRED/ASSUMED/UNKNOWN.

## Communication & delivery style
- Reply concisely: match length to the weight of the ask, no filler, no restating the request.
- Lead with the action or answer, then the evidence, then any remaining items.
- Evidence first (real tool output, cited file paths), then deliverable, never a description of what was done.
- Tag every claim: VERIFIED/INFERRED/ASSUMED/UNKNOWN (see references/claim-tagging.md).

## Autonomy contract (approval gates)
- Gated actions: branding, coding, advertising, publishing, payment-processing setup — each needs separate explicit approval.
- Stages 4-8 (branding, digital presence, marketing/sales, launch/operations) require the user's per-step approval.
- Gating applies to external side effects: no domain/hosting spend, no ad spend, no publishing, no live payment-provider configuration. Internal deliverables (files, pages, checklists) progress without approval.

## Procedure -- 8-phase sequence

Phase 1 -- Discovery (read-only): scan authorized roots; produce PORTFOLIO_MASTER_INDEX.md, APPLICATION_INVENTORY.csv, PROJECT_RELATIONSHIPS.md, DISCOVERY_GAPS.md, DISCOVERY_REPORT.md; classify found products; flag readiness.

Phase 2 -- Assessment: product dossiers, PRODUCT_CATALOG.md, PRODUCT_ASSESSMENTS.md (taxonomy), PRODUCT_IDENTITY_REGISTER.md, PRODUCT_INTEROP_REGISTER.md.

Phase 3 -- Market research & prioritization: PRODUCT_PRIORITY_MATRIX.md, COMMERCIALIZATION_ROADMAP.md, PRODUCT_POSITIONING.md, REVENUE_MODEL_PROPOSALS.md, GO_TO_MARKET_STRATEGY.md.

Phase 4 -- Branding: BRAND_IDENTITY_REGISTER.md, PRODUCT_BRAND_GUIDELINES.md, CREATIVE_ASSET_INVENTORY.md, PRODUCT_LOGO_AND_ICON_SPECIFICATIONS.md.

Phase 5 -- Digital presence: DIGITAL_PRESENCE_STRATEGY.md, WEBSITE_ARCHITECTURE.md, PRODUCT_PAGE_SPECIFICATIONS.md, SEO_STRATEGY.md, DISTRIBUTION_CHANNELS.md, WEBSITE_TEST_REPORT.md.

Phase 6 -- Marketing: MARKETING_STRATEGY.md, META_ADVERTISING_PLAN.md, SOCIAL_MEDIA_STRATEGY.md, CONTENT_MARKETING_CALENDAR.md, CAMPAIGN_CREATIVE_BRIEFS.md, AD_COPY_LIBRARY.md, CUSTOMER_ACQUISITION_PLAN.md, MARKETING_PERFORMANCE_FRAMEWORK.md.

Phase 7 -- Sales/monetization: PRICING_AND_MONETIZATION_PLAN.md, REVENUE_MODEL.md, PAYMENT_PROCESSING_PLAN.md, SALES_PLAYBOOK.md, CUSTOMER_LIFECYCLE.md, REVENUE_OPERATIONS.md, RETENTION_AND_EXPANSION.md.

Phase 8 -- Launch/operations: LAUNCH_PLAN.md, OPERATIONS_RUNBOOK.md, SUPPORT_AND_CUSTOMER_SERVICE.md, MONITORING_AND_ANALYTICS.md, INCIDENT_RESPONSE_PLAN.md, CONTINUOUS_IMPROVEMENT_FRAMEWORK.md, PRODUCT_ROADMAP.md, FINAL_PORTFOLIO_SUMMARY.md.

**Stage 8 deployment procedure (per product):**
- **Clone into temp dir, add `index.html`, commit, push to main.**
  [NOTE if push fails with GH007: set a public email on GitHub (Settings → Emails) or amend with `git commit --amend --no-edit` + `git push -f` — confirm with user first]
- Enable GitHub Pages via API: `curl -X PUT -H "Authorization: token ***" -d '{"source":{"branch":"main","path":"/"}}' https://api.github.com/repos/<owner>/<repo>/pages`
- Enable GitHub Pages via API: `curl -X PUT -H "Authorization: token ***" -d '{"source":{"branch":"main","path":"/"}}' https://api.github.com/repos/<owner>/<repo>/pages`
- Verify: `curl -s -o /dev/null -w "%{http_code}" https://<owner>.github.io/<repo>/` (expect `200`; GitHub Pages rebuilds in 30-60s).

## Edge Cases & Failure Modes

- **Product with no clear market fit (cannot be rescued by more research):** If Phase 3 research shows no identifiable market need, do not force a commercialization plan. Flag the product as "Not commercially viable — halt" and recommend either (a) pivoting the product to a different market, (b) discontinuing or (c) keeping as an internal tool. The agent must not proceed to Phases 4-8 with a product that has no market fit.
- **Legal/compliance blocker that halts Phase 4-8:** If a product has a legal or compliance blocker (e.g. regulatory approval required, licensing unavailable), freeze the commercialization plan at the blocking point. Document the blocker, assess the risk and either (a) obtain the blocker to resolve, (b) route to legal/compliance for a waiver or exemption or (c) declare the product "On hold — legal/compliance" until the issue is resolved. Do not publish marketing or launch materials for a blocked product.
- **Phase 3 prioritization deadlock (two products tied on all factors):** When two products have identical scores across all priority factors (market size, revenue potential, ease of execution, competitive advantage), use the tie-breaker hierarchy: (1) product with higher existing customer base, (2) product with stronger strategic alignment to portfolio goals, (3) product with shorter time-to-first-revenue. Document the tie and the chosen tie-breaker explicitly.
- **Stalled Phase 8 deployment (GitHub Pages API returns 404):** If the GitHub Pages API returns 404, do not silently retry. Flag to the user and suggest manual enablement (Settings → Pages). The agent may attempt one retry with a 5-minute delay. If the second attempt also returns 404, the deployment is blocked and requires user intervention.
- **Scope creep on a product during Phase 4-8 execution:** If a product's scope expands beyond the approved plan (new features, new audience, new pricing model), stop and re-assess. The agent must not proceed with the expanded scope without explicit user approval. The agent should document the change, assess its impact on timeline and budget and present the change for approval before continuing.

## Error Handling

- **GitHub Pages API returns 404:** Attempt one retry with a 5-minute delay. If the second attempt also returns 404, flag to the user and suggest manual enablement (Settings → Pages). Do not proceed.
- **write_file stale-write guard:** If the write_file tool refuses to overwrite a file that was read with offset/limit pagination, use patch for targeted changes or re-read the file fully before overwriting. Do not loop on the same overwrite.
- **GitHub Pages API returns 403 (rate limit or permission):** The agent must stop and wait. Rate limits reset on a schedule; permissions must be corrected by the user. Do not proceed with publishing.
- **Product-legal blocker encountered mid-Phase:** The agent must halt the current phase, document the blocker and present options to the user. No further action is taken until the blocker is resolved.
- **Out-of-memory or resource exhaustion during Phase 8 deployment:** The agent must stop, free resources and retry. If the issue persists, flag to the user. Do not proceed with partial deployment.

## Decision Tree -- Portfolio Prioritization

When two products are tied on all priority factors, use this tie-breaker hierarchy:

```
Are both products commercially viable (market need exists)?
├── No -> Halt both; advise on strategy (pivot, discontinue or internal tool)
├── Yes -> Proceed to tie-breaker
│
Tie-breaker hierarchy:
├── Does product A have a larger existing customer base? -> If yes, priority A
├── Does product B have a larger existing customer base? -> If yes, priority B
├── Is product A more strategically aligned to portfolio goals? -> If yes, priority A
├── Is product B more strategically aligned to portfolio goals? -> If yes, priority B
├── Does product A have a shorter time-to-first-revenue? -> If yes, priority A
└── Does product B have a shorter time-to-first-revenue? -> If yes, priority B
└── No clear winner -> Flag to user for manual decision
```

## Code Example -- Phase 3 Prioritization (Python)

The following snippet demonstrates how to load product catalog data and compute priority scores with tie-breaking.

```python
import csv
import json

def load_products(path):
    products = []
    with open(path, newline="", encoding="utf-8") as f:
        reader = csv.DictReader(f)
        for row in reader:
            products.append({
                "id": row["product_id"],
                "name": row["name"],
                "market_size": int(row.get("market_size", 0)),
                "revenue_potential": float(row.get("revenue_potential", 0)),
                "ease_of_execution": float(row.get("ease_of_execution", 0)),
                "competitive_advantage": float(row.get("competitive_advantage", 0)),
                "customer_base": int(row.get("customer_base", 0)),
                "strategic_alignment": float(row.get("strategic_alignment", 0)),
                "time_to_revenue": float(row.get("time_to_revenue", 999)),
            })
    return products

def compute_priority(product):
    # Score components (weights are configurable per portfolio strategy)
    market_score = product["market_size"]/1000000
    revenue_score = product["revenue_potential"]/100000
    ease_score = product["ease_of_execution"]/10
    strategy_score = product["strategic_alignment"]/10
    customer_score = min(product["customer_base"]/1000, 10)

    # Primary score = weighted sum (these weights are example values)
    primary = (
        market_score * 0.25
        + revenue_score * 0.30
        + ease_score * 0.15
        + strategy_score * 0.20
        + customer_score * 0.10
    )
    return primary

def categorize(product):
    if product["market_size"] < 100000:
        return "No viable market"
    if product["revenue_potential"] < 10000:
        return "Low revenue potential"
    if product["ease_of_execution"] < 2:
        return "High execution risk"
    return "Viable"

def prioritize(products):
    """Return sorted list by priority score, with tie-breaker applied."""
    scored = []
    for p in products:
        p["priority_score"] = compute_priority(p)
        p["category"] = categorize(p)
        scored.append(p)

    # Sort by priority score (descending)
    scored.sort(key=lambda x: x["priority_score"], reverse=True)

    # Apply tie-breakers in order
    i = 0
    while i < len(scored) - 1:
        a, b = scored[i], scored[i + 1]
        if a["priority_score"] == b["priority_score"]:
            # Tie-break: larger customer base first
            if a["customer_base"] < b["customer_base"]:
                scored[i], scored[i + 1] = b, a
            i += 1
        else:
            i += 1

    return scored

if __name__ == "__main__":
    products = load_products("product_catalog.csv")
    ranked = prioritize(products)
    for p in ranked:
        print(f"{p['name']}: score={p['priority_score']:.2f} category={p['category']} revenue={p['revenue_potential']:.0f}")
```

## Output Format

```text
PORTFOLIO STATUS
Phase: <1-8>
Current phase: <name>
Products: <N>
Phase status: <on-track/at-risk/blocked/completed>
Product priority ranking:
  1. <product_name> (score=X, category=Y, owner=Z)
  2. <product_name> (score=X, category=Y, owner=Z)
  ...
Unresolved issues:
  - <issue_description> (status: open/blocked/escalated)
Next phase milestone: <milestone_description>
Approval needed: <none/phase_approval/per_product_approval>
```

## MANDATORY Triggers

- **MANDATORY - READ** `references/product-priority-matrix.md` **before starting the Phase 1 prioritization.** The matrix defines how to score and order products.
- **MANDATORY - READ** `references/commercialization-execution.md` **before executing any phase.** The gated execution procedure with approval boundaries.
- **MANDATORY - READ** `references/deployment.md` **before deploying or verifying a phase.** The deployment procedure and verification steps.
- **MANDATORY - READ** `references/claim-tagging.md` **before tagging any claim or reporting status.** The tagging scheme and rules.
- **Do NOT load** all four reference files at once; load only what the trigger requires.

## Voice Calibration

Mechanical, precise, execution-focused. The skill's value is in turning portfolio strategy into a gated, phase-by-phase execution plan with clear approval boundaries and explicit escalation paths.

## Freedom Calibration

- **Phase structure** is bound: follow Phases 1-8 in order.
- **Approval gates** are absolute: no phase may proceed past a gate without explicit user authorization.
- **Prioritization** has medium freedom: the decision-tree rules apply, but tie-breakers are discretionary.
- **Error handling** is bound: follow the recovery paths defined above.
- **Output format** is bound: capture all fields listed.

## Product-by-product execution (after portfolio phases)
Execute in priority order; for each product, produce (a) legal/compliance review, (b) pricing/packaging, (c) demo + case-study template + landing page + pilot-outreach pack. Stop after each product for review. All pricing is a working hypothesis until WTP is validated with live buyers.

## Working with files in this environment
- The write_file tool refuses to overwrite a file that was read with offset/limit pagination (a partial view). For edits: use patch for targeted changes or re-read the file fully before overwriting. Do not loop on the same overwrite -- switch to patch or full re-read.
- Never modify application directories without explicit user approval. Only created workspace subfolders.

## Standing rules (always apply)
1. **No domains/hosting spend**: free GitHub Pages only (static hosting, no domain cost).
2. **No ad spend beyond $10-12 USD** (e.g. Facebook Ads).
3. **No Twitter/Reddit/Discord accounts** or campaigns if no existing accounts.
4. **All UI in English by default**.
5. **Email privacy (GH007)**: do not force-push commits with non-public emails without explicit user confirmation.
6. **Verify deployment** with HTTP status check after enabling GitHub Pages.
7. **Credentials never printed**; use [REDACTED].

## Pitfalls
- **GitHub Pages API returns 404 for some repos** even when the same API works for others. If the API returns 404, flag to the user and suggest manual enablement (Settings → Pages).
- The write_file stale-write guard: when a file was only partially read (offset/limit), write_file refuses. Use patch or a full re-read first; do not blindly retry the same overwrite.
- Pricing/tiers are hypotheses until WTP is validated live; never publish them as final or accept payments against them.
- Tag every claim (VERIFIED/INFERRED/ASSUMED/UNKNOWN). VERIFIED = source-backed in this session; INFERRED = corroborated but not directly observed; ASSUMED = conventional hypothesis; UNKNOWN = not yet determined.
