# Wholeness Within Co — 30-Day Shopify Growth Engineering Roadmap

## Executive Audit Summary

### Current repo status (as of May 13, 2026)
- The repository does **not** yet contain Shopify theme source directories (`layout/`, `templates/`, `sections/`, `snippets/`, `assets/`, `config/`).
- Because of that, the store cannot yet be improved through branch/PR-based theme code updates in this repo.

### P0 blocker
Before conversion/SEO work can ship, we must first pull the current published theme into this repository and set up a safe Shopify CLI workflow.

---

## How this plan is prioritized
Prioritization is based on expected impact + implementation speed + risk control:
1. **Foundation first** (safe Git + preview workflow)
2. **Conversion pages next** (homepage + PDP)
3. **Email capture + landing pages**
4. **SEO + trust/storytelling content**
5. **Performance + AOV enhancements**

---

## 30-Day Implementation Plan (Actionable)

## Phase 0 — Foundation & Governance (Days 1–3)

### Summary of changes
- Set up Shopify CLI + GitHub workflow for non-live development.
- Create unpublished theme preview protocol for every major release.
- Add guardrails to prevent secrets and restricted operational edits.

### Files changed
- `.gitignore`
- `.env.example`
- `docs/SHOPIFY_WORKFLOW.md`
- `docs/PREVIEW_RELEASE_PROCESS.md`
- `docs/ROLLBACK_RUNBOOK.md`
- `.github/pull_request_template.md`

### Reason for change
This removes the highest risk: accidental live edits and non-reversible production changes.

### Expected business impact
- Faster and safer release cycle
- Lower incident risk during merchandising/CRO experiments
- Clear ownership and QA standards

### Testing checklist
- [ ] `shopify version` returns installed CLI version
- [ ] `shopify theme pull --store <store-url> --theme <theme-id>` completes successfully
- [ ] `shopify theme dev --store <store-url>` runs local preview
- [ ] `.env` is ignored and no secrets appear in `git status`
- [ ] Unpublished preview theme link is generated and shareable

### Rollback instructions
- Revert PR and redeploy previous stable theme version
- Republish previous live theme in Shopify admin if preview deployment regresses

---

## Phase 1 — Homepage + Product Page Conversion Lift (Days 4–10)

### Summary of changes
- Improve homepage message clarity, CTA hierarchy, and trust proof.
- Improve PDP purchase flow (mobile sticky ATC, benefits-first content, objections handling).

### Files changed
- `sections/main-hero.liquid` (or equivalent)
- `sections/main-product.liquid`
- `snippets/trust-badges.liquid`
- `snippets/product-benefits.liquid`
- `assets/theme.css`
- `assets/theme.js`

### Reason for change
Homepage + PDP are primary conversion nodes and typically provide the fastest revenue lift.

### Expected business impact
- Increased add-to-cart rate
- Improved mobile conversion rate
- Lower decision friction before checkout

### Testing checklist
- [ ] Mobile sticky ATC works on iOS Safari + Android Chrome
- [ ] Variant selection + ATC + quantity adjustments function correctly
- [ ] Trust badges and FAQ content render without layout shift
- [ ] No JavaScript errors in browser console
- [ ] Preview QA signoff captured in PR

### Rollback instructions
- Revert phase PR
- Re-publish previous approved unpublished theme snapshot

---

## Phase 2 — Email Capture + Campaign Landing System (Days 11–16)

### Summary of changes
- Add high-quality email lead capture sections and dedicated campaign landing template.
- Implement lead magnet module for paid traffic and organic lead generation.

### Files changed
- `sections/email-capture.liquid`
- `templates/page.landing.json`
- `templates/page.lead-magnet.json`
- `snippets/form-feedback.liquid`

### Reason for change
Owned audience growth (email/SMS) improves LTV and reduces dependency on paid reacquisition.

### Expected business impact
- Higher subscriber acquisition rate
- Improved conversion of cold campaign traffic
- Better recovery and repeat purchase potential

### Testing checklist
- [ ] Form validation states pass on desktop/mobile
- [ ] Form submission event(s) fire for analytics stack
- [ ] UTM links route to correct landing variants
- [ ] Thank-you/success UI is visible and accessible

### Rollback instructions
- Disable new lead-gen sections in theme editor
- Revert PR and restore previous theme preview

---

## Phase 3 — SEO + Content + Trust Authority (Days 17–23)

### Summary of changes
- Improve technical + on-page metadata quality.
- Add article/blog layout optimized for ingredient education and product storytelling.
- Expand trust modules (testimonials, FAQs, expert framing).

### Files changed
- `layout/theme.liquid`
- `snippets/seo-meta.liquid`
- `templates/article.json`
- `sections/main-article.liquid`
- `sections/testimonials.liquid`
- `sections/faq.liquid`

### Reason for change
SEO and educational trust content compound traffic while improving conversion confidence.

### Expected business impact
- Improved organic impressions and click-through
- More qualified top-funnel sessions
- Better PDP confidence and reduced hesitation

### Testing checklist
- [ ] Metadata is present and accurate for homepage, collection, product, article
- [ ] Structured data validates without critical errors
- [ ] Internal links connect educational pages to product pages
- [ ] FAQ/testimonial modules are performant and mobile-friendly

### Rollback instructions
- Revert metadata/content PRs
- Restore prior stable theme version from preview history

---

## Phase 4 — Speed + Mobile Polish + AOV Components (Days 24–30)

### Summary of changes
- Improve front-end performance and mobile readability.
- Add bundle/upsell presentation components (visual/layout only unless approved).

### Files changed
- `assets/theme.css`
- `assets/theme.js`
- `snippets/responsive-image.liquid`
- `sections/upsell-bundle-concept.liquid`
- `docs/EXPERIMENT_BACKLOG.md`

### Reason for change
Performance and merchandising clarity improve both conversion and average order value.

### Expected business impact
- Faster pages and reduced bounce
- Better mobile completion rates
- Higher AOV from bundle visibility

### Testing checklist
- [ ] Lighthouse mobile performance trend improves vs baseline
- [ ] LCP/CLS on homepage and PDP do not regress
- [ ] Upsell module does not interrupt ATC flow
- [ ] CSS/JS additions do not inflate payload unnecessarily

### Rollback instructions
- Remove new performance/upsell components from theme
- Revert PR and redeploy previous version

---

## KPI Targets for First 30 Days (after theme import)

Track weekly with baseline captured on Day 1 of implementation:
- Conversion Rate (overall, mobile)
- Add-to-Cart Rate
- Checkout Initiation Rate
- Revenue per Session
- Email Opt-in Rate
- Organic Sessions + Organic CTR
- LCP + CLS (homepage and PDP)

Recommended initial directional targets:
- +10–20% ATC rate improvement
- +15–30% email opt-in rate improvement
- +5–12% mobile CVR improvement
- -10–25% homepage/PDP LCP time improvement

---

## First 5 Execution Tasks (immediately next)

1. Connect Shopify store to GitHub repo branch strategy.
2. Pull published theme into this repository.
3. Create `.env.example` and verify secret-safe local setup.
4. Create first unpublished preview theme and share URL.
5. Open Phase 1 PR with homepage + PDP implementation checklist.

> Once these five tasks are done, I can begin shipping daily conversion-focused PRs in this repo with preview links and rollback notes.
