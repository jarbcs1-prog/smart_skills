# Commercialization execution protocol

Staged execution with explicit gate states, per the 8-phase commercialization sequence. This document defines what each phase completes, which actions are gated and the autonomy level granted per phase.

## Stage state machine

| Stage | Name | Deliverable | Gate |
|-------|------|-------------|------|
| 1 | Discovery | PORTFOLIO_MASTER_INDEX.md, APPLICATION_INVENTORY.csv, PROJECT_RELATIONSHIPS.md, DISCOVERY_GAPS.md, DISCOVERY_REPORT.md | Read-only scope |
| 2 | Assessment | Products dossiers, PRODUCT_CATALOG.md, PRODUCT_ASSESSMENTS.md, PRODUCT_IDENTITY_REGISTER.md, PRODUCT_INTEROP_REGISTER.md | Read-only scope |
| 3 | Market research & prioritization | PRODUCT_PRIORITY_MATRIX.md, COMMERCIALIZATION_ROADMAP.md, PRODUCT_POSITIONING.md, REVENUE_MODEL_PROPOSALS.md, GO_TO_MARKET_STRATEGY.md | Read-only scope |
| 4 | Branding | BRAND_IDENTITY_REGISTER.md, PRODUCT_BRAND_GUIDELINES.md, CREATIVE_ASSET_INVENTORY.md, PRODUCT_LOGO_AND_ICON_SPECIFICATIONS.md | Approve + brand assets |
| 5 | Digital presence | DIGITAL_PRESENCE_STRATEGY.md, WEBSITE_ARCHITECTURE.md, PRODUCT_PAGE_SPECIFICATIONS.md, SEO_STRATEGY.md, DISTRIBUTION_CHANNELS.md, WEBSITE_TEST_REPORT.md | Approve + build websites |
| 6 | Marketing | MARKETING_STRATEGY.md, META_ADVERTISING_PLAN.md, SOCIAL_MEDIA_STRATEGY.md, CONTENT_MARKETING_CALENDAR.md, CAMPAIGN_CREATIVE_BRIEFS.md, AD_COPY_LIBRARY.md, CUSTOMER_ACQUISITION_PLAN.md, MARKETING_PERFORMANCE_FRAMEWORK.md | Approve + campaigns |
| 7 | Sales/monetization | PRICING_AND_MONETIZATION_PLAN.md, REVENUE_MODEL.md, PAYMENT_PROCESSING_PLAN.md, SALES_PLAYBOOK.md, CUSTOMER_LIFECYCLE.md, REVENUE_OPERATIONS.md, RETENTION_AND_EXPANSION.md | Approve + payment setup |
| 8 | Launch/operations | LAUNCH_PLAN.md, OPERATIONS_RUNBOOK.md, SUPPORT_AND_CUSTOMER_SERVICE.md, MONITORING_AND_ANALYTICS.md, INCIDENT_RESPONSE_PLAN.md, CONTINUOUS_IMPROVEMENT_FRAMEWORK.md, PRODUCT_ROADMAP.md, FINAL_PORTFOLIO_SUMMARY.md | Full approval + go-live |

## Autonomy levels (settled in this portfolio)

| Stage | Autonomy granted | What still requires approval |
|-------|------------------|------------------------------|
| 4 (branding) | Finalize brand assets, guidelines, creative asset inventory | Approval of brand before external use |
| 5 (digital presence) | Build product landing pages, stage files on local drive | Domain registration, hosting spend |
| 6 (marketing) | Write creative briefs, ad copy, content calendar, email templates, blog outlines | Ad platform accounts, ad spend, publishing |
| 7 (sales/monetization) | Finalize pricing tiers (hypothesis), payment processing plan, sales playbook | Live payment-provider configuration |
| 8 (launch/operations) | Prepare launch checklist, readiness gate | All gating actions |

## Gate rules (always apply)

1. No external side effects (domains, ad spend, publishing, live payments) without explicit user approval.
2. Internal deliverables (files, pages, checklists) progress without approval.
3. All claims tagged VERIFIED/INFERRED/ASSUMED/UNKNOWN.
4. Credentials never printed; use [REDACTED].
5. Single source of truth: C:/{project-root}/PRODUCT_PORTFOLIO.
6. Product priority order list.
7. All UI in English by default.
8. User's style: lead with action, then evidence, then items. Concise, no filler.

## Related
- references/claim-tagging.md
- references/product-priority-matrix.md
