---
name: portfolio-commercialization
description: AI-agent product commercialization in 8 gated phases.
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

Class-level skill for systematic commercialization of an AI/agent software product portfolio through an 8-phase sequence with staged approval gates, read-only discovery, claim tagging and per-product milestone execution.

## When to use
- Beginning any portfolio commercialization engagement
- Re-ordering or re-prioritizing products in the portfolio
- Auditing whether a phase or action is approved or still gated

## Communication & delivery style
- Reply concisly: match length to the weight of the ask, no filler, no restating the request.
- Lead with the action or answer, then the evidence, then any remaining items.
- Evidence first (real tool output, cited file paths), then deliverable, never a description of what was done.
- Tag every claim: VERIFIED/INFERRED/ASSUMED/UNKNOWN (see references/claim-tagging.md).

## Autonomy contract (approval gates)
- Gated actions: branding, coding, advertising, publishing, payment-processing setup — each needs separate explicit approval.
- Stages 4-8 (branding, digital presence, marketing/sales, launch/operations) require the user's per-step approval.
- Gating applies to external side effects: no domain/hosting spend, no ad spend, no publishing, no live payment-provider configuration. Internal deliverables (files, pages, checklists) progress without approval.

## Procedure -- 8-phase sequence

Phase 1 -- Discovery (read-only): scan authorized roots; produce PORTFOLIO_MASTER_INDEX.md, APPLICATION_INVENTORY.csv, PROJECT_RELATIONSHIPS.md, DISCOVERY_GAPS.md, DISCOVERY_REPORT.md; classify products; flag readiness.

Phase 2 -- Assessment: products dossiers, PRODUCT_CATALOG.md, PRODUCT_ASSESSMENTS.md (taxonomy), PRODUCT_IDENTITY_REGISTER.md, PRODUCT_INTEROP_REGISTER.md.

Phase 3 -- Market research & prioritization: PRODUCT_PRIORITY_MATRIX.md, COMMERCIALIZATION_ROADMAP.md, PRODUCT_POSITIONING.md, REVENUE_MODEL_PROPOSALS.md, GO_TO_MARKET_STRATEGY.md.

Phase 4 -- Branding: BRAND_IDENTITY_REGISTER.md, PRODUCT_BRAND_GUIDELINES.md, CREATIVE_ASSET_INVENTORY.md, PRODUCT_LOGO_AND_ICON_SPECIFICATIONS.md.

Phase 5 -- Digital presence: DIGITAL_PRESENCE_STRATEGY.md, WEBSITE_ARCHITECTURE.md, PRODUCT_PAGE_SPECIFICATIONS.md, SEO_STRATEGY.md, DISTRIBUTION_CHANNELS.md, WEBSITE_TEST_REPORT.md.

Phase 6 -- Marketing: MARKETING_STRATEGY.md, META_ADVERTISING_PLAN.md, SOCIAL_MEDIA_STRATEGY.md, CONTENT_MARKETING_CALENDAR.md, CAMPAIGN_CREATIVE_BRIEFS.md, AD_COPY_LIBRARY.md, CUSTOMER_ACQUISITION_PLAN.md, MARKETING_PERFORMANCE_FRAMEWORK.md.

Phase 7 -- Sales/monetization: PRICING_AND_MONETIZATION_PLAN.md, REVENUE_MODEL.md, PAYMENT_PROCESSING_PLAN.md, SALES_PLAYBOOK.md, CUSTOMER_LIFECYCLE.md, REVENUE_OPERATIONS.md, RETENTION_AND_EXPANSION.md.

Phase 8 -- Launch/operations: LAUNCH_PLAN.md, OPERATIONS_RUNBOOK.md, SUPPORT_AND_CUSTOMER_SERVICE.md, MONITORING_AND_ANALYTICS.md, INCIDENT_RESPONSE_PLAN.md, CONTINUOUS_IMPROVEMENT_FRAMEWORK.md, PRODUCT_ROADMAP.md, FINAL_PORTFOLIO_SUMMARY.md.

## Product-by-product execution (after portfolio phases)
Execute in priority order; for each product, produce (a) legal/compliance review, (b) pricing/packaging, (c) demo + case-study template + landing page + pilot-outreach pack. Stop after each product for review. All pricing is a working hypothesis until WTP is validated with live buyers.

## Working with files in this environment
- The write_file tool refuses to overwrite a file that was read with offset/limit pagination (a partial view). For edits: use patch for targeted changes or re-read the file fully before overwriting. Do not loop on the same overwrite -- switch to patch or full re-read.
- Never modify application directories without explicit user approval. Only created workspace subfolders.

## Pitfalls
- The write_file stale-write guard: when a file was only partially read (offset/limit), write_file refuses. Use patch or a full re-read first; do not blindly retry the same overwrite.
- Pricing/tiers are hypotheses until WTP is validated live; never publish them as final or accept payments against them.
- Tag every claim (VERIFIED/INFERRED/ASSUMED/UNKNOWN). VERIFIED = source-backed in this session; INFERRED = corroborated but not directly observed; ASSUMED = conventional hypothesis; UNKNOWN = not yet determined.