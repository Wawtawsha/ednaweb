# Roadmap: EDNA SSIS Framework Landing Page

## Overview

Build a conversion-optimized landing page for Andy Leonard's SSIS Framework product (available NOW for purchase) and the broader DILM Suite ecosystem. SSIS Framework is a metadata-driven orchestration framework that completes the SSIS Catalog. The page must look like a modern data engineering tool (dbt/Dagster/Prefect quality), not legacy Microsoft, and convert SSIS professionals into customers through problem-oriented messaging, Andy's decades of credibility, and frictionless lead capture. The page showcases SSIS Framework as the hero product with cross-sell to Catalog Compare ($4,995/yr), training courses, and the full DILM Suite. Static HTML + Tailwind CSS on Vercel. Three phases: ship the visual page, add privacy-compliant tracking, then wire up lead capture and integrations.

## Phases

**Phase Numbering:**
- Integer phases (1, 2, 3): Planned milestone work
- Decimal phases (2.1, 2.2): Urgent insertions (marked with INSERTED)

Decimal phases appear between their surrounding integers in numeric order.

- [ ] **Phase 1: Visual Page** - Complete landing page with all 12 sections, design system, responsive layout, SEO, and Vercel deployment
- [ ] **Phase 2: Privacy + Tracking** - Cookie consent banner and all analytics (Nessus CRM, GA4, Clarity) gated behind consent
- [ ] **Phase 3: Lead Capture + Integrations** - Newsletter form, contact/consultation forms, Calendly embed, Nessus CRM lead capture

## Phase Details

### Phase 1: Visual Page
**Goal**: A visitor arriving from Andy's LinkedIn post sees a professional, modern landing page that articulates the SSIS Framework value proposition and looks competitive with dbt/Dagster/Prefect
**Depends on**: Nothing (first phase)
**Requirements**: PAGE-01, PAGE-02, PAGE-03, PAGE-04, PAGE-05, PAGE-06, PAGE-07, PAGE-08, PAGE-09, PAGE-10, PAGE-11, PAGE-12, DSGN-01, DSGN-02, DSGN-03, DSGN-04, SEO-01, SEO-02, DEPL-01
**Success Criteria** (what must be TRUE):
  1. Visitor sees a dark-themed, modern data engineering landing page at the Vercel URL that does NOT look like legacy Microsoft documentation
  2. Visitor can read the hero headline, understand what SSIS Framework does, and see the stored procedure code snippet within 5 seconds of page load
  3. Visitor can navigate all 12 sections (hero, trust strip, problem, solution, features, pricing, about, testimonials, newsletter, FAQ, final CTA, footer) on both mobile and desktop without layout breaks
  4. Page shared on LinkedIn renders a compelling Open Graph preview card with correct title, description, and image
  5. Lighthouse scores 95+ performance, 90+ accessibility, page loads in under 2 seconds on mobile 3G simulation
**Plans**: TBD

Plans:
- [ ] 01-01: Project scaffolding, Tailwind config, design system tokens, and file structure
- [ ] 01-02: Hero section, navigation, trust strip, and problem/solution narrative sections
- [ ] 01-03: Features, pricing, credibility, testimonials, FAQ, final CTA, and footer sections
- [ ] 01-04: Mobile responsiveness, accessibility audit, SEO metadata, privacy policy page, and Vercel deployment

### Phase 2: Privacy + Tracking
**Goal**: Every visitor interaction is measured accurately, and no tracking fires without explicit cookie consent
**Depends on**: Phase 1 (page must exist before tracking can measure it; stable page structure required for scroll tracking)
**Requirements**: PRIV-01, TRCK-01, TRCK-02, TRCK-03
**Success Criteria** (what must be TRUE):
  1. First-time visitor sees a non-blocking bottom cookie banner with equal-prominence Accept/Reject buttons before any third-party tracking cookie is set
  2. Visitor who rejects cookies can browse the entire page with full functionality and zero tracking scripts loaded (verifiable in browser DevTools Network tab)
  3. Visitor who accepts cookies generates events in GA4 (page view, scroll depth at 25/50/75/90%), Microsoft Clarity (session recording), and Nessus CRM (page view, scroll depth, time-on-page, CTA clicks)
  4. Cookie consent persists across sessions (12-month expiry) and does not re-prompt on return visits
**Plans**: TBD

Plans:
- [ ] 02-01: Cookie consent banner implementation with geo-targeting and consent state management
- [ ] 02-02: GA4, Microsoft Clarity, and Nessus CRM tracking scripts gated behind consent with custom event instrumentation

### Phase 3: Lead Capture + Integrations
**Goal**: Visitors can take action -- sign up for the newsletter, request a consultation via Calendly, or submit a contact form -- and all leads flow into Nessus CRM
**Depends on**: Phase 2 (lead capture forms generate tracking events; Nessus CRM integration must be active for lead data to flow)
**Requirements**: LEAD-01, LEAD-02, LEAD-03, INTG-01
**Success Criteria** (what must be TRUE):
  1. Visitor can submit their email in the newsletter signup form and see immediate visual confirmation (no duplicate submissions, no blank-screen failure)
  2. Visitor can click the consultation CTA and book a meeting through Calendly (embedded widget or direct link) without leaving the page flow
  3. Visitor can submit a contact/consultation form (name, email, company max) and the submission routes to Nessus CRM as a captured lead
  4. All form submissions fire corresponding GA4 and Nessus CRM tracking events (newsletter_signup, calendly_click, consultation_request)
**Plans**: TBD

Plans:
- [ ] 03-01: Newsletter signup form with value preview, email validation, submission feedback, and backend integration
- [ ] 03-02: Calendly embed, contact/consultation form, Nessus CRM lead capture integration, and tracking event wiring

## Progress

**Execution Order:**
Phases execute in numeric order: 1 --> 2 --> 3

| Phase | Plans Complete | Status | Completed |
|-------|---------------|--------|-----------|
| 1. Visual Page | 0/4 | Not started | - |
| 2. Privacy + Tracking | 0/2 | Not started | - |
| 3. Lead Capture + Integrations | 0/2 | Not started | - |
