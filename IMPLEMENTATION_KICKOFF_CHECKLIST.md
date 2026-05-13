# Wholeness Within Co. — Implementation Kickoff Checklist

Date: May 13, 2026

You confirmed access is available. This checklist converts strategy into immediate execution tasks for Shopify CLI + GitHub workflow and the first redesign sprint.

## 1) Access & Environment Setup (Required before any theme edits)

### Confirm access
- [ ] Shopify store admin access confirmed
- [ ] Permission to manage themes confirmed
- [ ] Permission to create unpublished themes confirmed
- [ ] GitHub repo write access confirmed

### Local environment variables
Create a local `.env` file (do not commit) with:

```bash
SHOPIFY_FLAG_STORE=wholeness-withinco.myshopify.com
SHOPIFY_CLI_THEME_TOKEN=YOUR_THEME_ACCESS_TOKEN
```

> Keep tokens only in environment variables. Never commit credentials.

## 2) Initialize Safe Theme Workflow

### Branch conventions
- `feat/homepage-luxury-redesign`
- `feat/collection-conversion-upgrade`
- `feat/pdp-trust-stack`
- `fix/mobile-ux-polish`

### Core workflow commands
```bash
# 1) Authenticate
shopify auth logout || true
shopify auth login --store "$SHOPIFY_FLAG_STORE"

# 2) Pull current live theme into repo
shopify theme pull --store "$SHOPIFY_FLAG_STORE"

# 3) Create working branch
git checkout -b feat/homepage-luxury-redesign

# 4) Start local preview
shopify theme dev --store "$SHOPIFY_FLAG_STORE"

# 5) Push to unpublished preview theme (major milestones)
shopify theme push --unpublished --store "$SHOPIFY_FLAG_STORE" --theme "Wholeness Preview - Sprint 1"
```

## 3) First Build Sprint (Professional Redesign)

## Sprint 1 objective (5 days)
Ship a professional homepage + collection experience that increases trust and click-through without checkout changes.

### Day 1: Homepage hero + trust rail
- [ ] Replace promo-first hero with brand-first hero
- [ ] Add primary CTA: “Shop by Skin Concern”
- [ ] Add secondary CTA: “Take the Ritual Quiz”
- [ ] Add trust rail (small-batch, non-toxic, sensitive-skin safe)

### Day 2: Concern-based collection navigation
- [ ] Add concern cards: Sensitivity / Barrier Repair / Hydration / Glow
- [ ] Normalize collection naming and capitalization
- [ ] Improve nav labels and reduce ambiguity

### Day 3: Product-grid conversion cards
- [ ] Add product benefit microcopy under titles
- [ ] Add badges: Best Seller / Sensitive-Skin Safe / Unscented
- [ ] Add quick-add CTA on collection cards

### Day 4: Blog-to-revenue blocks
- [ ] Add in-article product callout module
- [ ] Add mid-article and end-of-article lead magnet CTA
- [ ] Add “Shop this routine” block

### Day 5: QA and publish preview
- [ ] Mobile QA (iOS + Android)
- [ ] Performance QA (image sizes + lazy loading)
- [ ] Accessibility checks (contrast, heading order, button labels)
- [ ] Share unpublished theme preview URL for approval

## 4) PR Template Requirements (every PR)

Each PR must include:
1. Summary of changes
2. Files changed
3. Reason for change
4. Expected business impact
5. Testing checklist
6. Rollback instructions
7. Unpublished preview URL

## 5) Rollback Procedure

If any regression occurs:
1. Revert PR in GitHub.
2. Re-publish previously stable Shopify theme.
3. Re-run QA checklist on rollback theme.
4. Open hotfix PR with root-cause notes.

## 6) KPI Baseline Snapshot (capture before Sprint 1 goes live)

- Conversion rate (overall/mobile)
- Add-to-cart rate
- Checkout initiation rate
- AOV
- Revenue per session
- Email opt-in rate
- Returning customer rate
- LCP/CLS for homepage + top PDP

## 7) Definition of Done for Sprint 1

Sprint is done only when:
- [ ] Homepage redesign is live in **unpublished preview theme**
- [ ] Collection card experience upgraded and QA-passed
- [ ] PR approved with full checklist + rollback notes
- [ ] Baseline vs preview KPI hypothesis logged
- [ ] No changes made to restricted systems (checkout/payment/tax/shipping/inventory/customer data)

