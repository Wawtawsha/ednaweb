# Requirements: EDNA SSIS Framework Landing Page

**Defined:** 2026-03-03
**Core Value:** Convert SSIS professionals into SSIS Framework customers through a modern, conversion-optimized landing page that amplifies Andy Leonard's credibility

## v1 Requirements

Requirements for initial release. Each maps to roadmap phases.

### Page Structure

- [ ] **PAGE-01**: Centered hero section with problem-oriented headline (<8 words), dual CTAs (Purchase/Schedule Consultation primary, Newsletter secondary), and syntax-highlighted stored procedure code snippet
- [ ] **PAGE-02**: Sticky navigation bar with persistent CTA button visible during scroll
- [ ] **PAGE-03**: Trust strip below hero displaying Andy's credentials as metrics (years, books, MVP status, packages orchestrated)
- [ ] **PAGE-04**: Problem section articulating SSIS Catalog gaps using PAS framework with Andy's direct quotes
- [ ] **PAGE-05**: Solution section with before/after code comparison (manual T-SQL vs. one stored procedure call)
- [ ] **PAGE-06**: Feature blocks in chess layout (alternating text/visual) with problem-oriented headlines
- [ ] **PAGE-07**: Edition/pricing comparison table with placeholder pricing ready for Andy's actual numbers
- [ ] **PAGE-08**: About Andy/EDNA credibility section with bio, credentials, and photo
- [ ] **PAGE-09**: Testimonials section with placeholder structure for real quotes (name, title, company, quantified result)
- [ ] **PAGE-10**: DILM Suite ecosystem section showcasing Catalog Compare ($4,995/yr), training courses (SSIS Premium $199/yr, Premium Level $749/yr), and other tools as cross-sell opportunities
- [ ] **PAGE-10B**: FAQ section with accordion format (6-8 questions covering ROI, process, editions, migration)
- [ ] **PAGE-11**: Final full-width CTA block with visually distinct background
- [ ] **PAGE-12**: Footer with EDNA logo, navigation links, social links, legal links

### Design

- [ ] **DSGN-01**: Dark theme using EDNA brand colors (Black #000000, Green #18a05c/#76e49e, Rose #cd2653) that matches modern data engineering tool quality (dbt, Dagster, Prefect level)
- [ ] **DSGN-02**: Inter font for body/headings with JetBrains Mono for code blocks, fluid typography with clamp()
- [ ] **DSGN-03**: Mobile-first responsive design tested on iPhone SE through desktop (68% of B2B buyers research on mobile)
- [ ] **DSGN-04**: WCAG 2.1 AA accessibility compliance (minimum 4.5:1 contrast ratio on all text)

### SEO & Social

- [ ] **SEO-01**: Complete meta tags, Open Graph tags, Twitter Card tags, and structured data (SoftwareApplication schema) for LinkedIn sharing optimization
- [ ] **SEO-02**: Privacy policy page (required for cookie consent and legal compliance)

### Privacy & Consent

- [ ] **PRIV-01**: Cookie consent banner (bottom bar, non-blocking) with equal-prominence Accept/Reject buttons, geo-targeted behavior (GDPR opt-in for EU, CCPA opt-out for US), all non-essential cookies defaulting to OFF

### Tracking & Analytics

- [ ] **TRCK-01**: Nessus CRM integration via vanilla JS (page views, scroll depth, time-on-page, section visibility, CTA clicks, custom events) gated behind cookie consent
- [ ] **TRCK-02**: GA4 analytics with custom scroll depth events (25/50/75/90%) gated behind cookie consent
- [ ] **TRCK-03**: Microsoft Clarity heatmaps and session recordings gated behind cookie consent

### Lead Capture

- [ ] **LEAD-01**: Newsletter signup form with value preview (past topics, subscriber count) and email-only progressive profiling
- [ ] **LEAD-02**: Nessus CRM lead capture form integration for consultation requests
- [ ] **LEAD-03**: Contact form for enterprise inquiries (name, email, company maximum)

### Integrations

- [ ] **INTG-01**: Calendly integration for consultation booking (embedded widget or direct link with fallback email)

### Deployment

- [ ] **DEPL-01**: Deployed to Vercel as static site with sub-2-second LCP, Lighthouse 95+ performance score, <500KB total page weight

## v2 Requirements

Deferred to future release. Tracked but not in current roadmap.

### Optimization

- **OPT-01**: A/B testing of hero headline, CTA copy, and layout variants (requires ~1000 visitors/month baseline)
- **OPT-02**: Lead scoring model with behavioral point assignments for CRM integration
- **OPT-03**: Blog integration surfacing Andy's recent posts as credibility signals

### Community

- **COMM-01**: Lead magnet download ("SSIS to Fabric Migration Checklist" or similar) with email gate
- **COMM-02**: SQL Server 2016 EOL urgency eyebrow banner (time-sensitive, July 2026)

## Out of Scope

| Feature | Reason |
|---------|--------|
| Community Edition CTA | User unsure if SSIS Framework will have community edition -- explicitly excluded per user decision |
| Chatbot / AI assistant | Data engineers despise chatbots; signals poor docs (Evil Martians research) |
| Auto-playing video | 73% of users dislike autoplay; hostile UX |
| Exit-intent popups | Interrupt-driven marketing alienates technical audiences |
| Heavy animations (Rive/Lottie/3D) | Slows page load, distracts from content; Airbyte's approach feels slower than Prefect's clean approach |
| Feature comparison with competitors | Feels defensive; SSIS Framework is the only framework for SSIS -- no comparison needed |
| Pricing calculator | Pricing not public; wrong numbers worse than none |
| Multiple competing CTAs | Research shows this reduces conversions via choice paralysis |
| Build step / JavaScript framework | Single static page; Next.js/Astro adds 80-100KB+ overhead for zero benefit |
| Side-by-side hero layout | Evil Martians: centered is dominant and more trustworthy for devtools |

## Traceability

| Requirement | Phase | Status |
|-------------|-------|--------|
| PAGE-01 | Phase 1 | Pending |
| PAGE-02 | Phase 1 | Pending |
| PAGE-03 | Phase 1 | Pending |
| PAGE-04 | Phase 1 | Pending |
| PAGE-05 | Phase 1 | Pending |
| PAGE-06 | Phase 1 | Pending |
| PAGE-07 | Phase 1 | Pending |
| PAGE-08 | Phase 1 | Pending |
| PAGE-09 | Phase 1 | Pending |
| PAGE-10 | Phase 1 | Pending |
| PAGE-11 | Phase 1 | Pending |
| PAGE-12 | Phase 1 | Pending |
| DSGN-01 | Phase 1 | Pending |
| DSGN-02 | Phase 1 | Pending |
| DSGN-03 | Phase 1 | Pending |
| DSGN-04 | Phase 1 | Pending |
| SEO-01 | Phase 1 | Pending |
| SEO-02 | Phase 1 | Pending |
| DEPL-01 | Phase 1 | Pending |
| PRIV-01 | Phase 2 | Pending |
| TRCK-01 | Phase 2 | Pending |
| TRCK-02 | Phase 2 | Pending |
| TRCK-03 | Phase 2 | Pending |
| LEAD-01 | Phase 3 | Pending |
| LEAD-02 | Phase 3 | Pending |
| LEAD-03 | Phase 3 | Pending |
| INTG-01 | Phase 3 | Pending |

**Coverage:**
- v1 requirements: 27 total
- Mapped to phases: 27
- Unmapped: 0

---
*Requirements defined: 2026-03-03*
*Last updated: 2026-03-03 after initial definition*
