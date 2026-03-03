# EDNA SSIS Framework Landing Page

## What This Is

A conversion-optimized landing page for EDNA's SSIS Framework product -- a metadata-driven orchestration framework that completes the SSIS Catalog (which Microsoft never shipped with proper orchestration). The page targets SSIS professionals and enterprise data engineers, selling the commercial product and offering consultation booking through Andy Leonard's credibility.

## Core Value

A visitor arriving from Andy's LinkedIn post can understand what SSIS Framework does, why they need it, and take action (purchase or schedule consultation) within a single page visit.

## Requirements

### Validated

(None yet -- ship to validate)

### Active

See: .planning/REQUIREMENTS.md for full checkable requirements (27 v1 requirements across 7 categories).

Summary:
- 12 page sections (hero through footer)
- 4 design requirements (dark theme, typography, responsive, accessibility)
- 2 SEO requirements (meta tags, privacy policy)
- 1 privacy requirement (cookie consent)
- 3 tracking requirements (Nessus CRM, GA4, Clarity)
- 3 lead capture requirements (newsletter, consultation form, contact form)
- 1 integration requirement (Calendly)
- 1 deployment requirement (Vercel, performance targets)

### Out of Scope

- Community Edition CTA -- user unsure if it will exist
- Chatbot / AI assistant -- alienates technical audiences
- Auto-playing video -- hostile UX
- Exit-intent popups -- interrupt marketing alienates data engineers
- Heavy animations -- slows load, distracts
- Build step / JavaScript framework -- single page, zero benefit
- A/B testing -- deferred to v2, requires traffic baseline
- Blog integration -- deferred to v2

## Context

- EDNA (Enterprise Data & Analytics) is Andy Leonard's company
- Andy is a Microsoft MVP, author of 12+ books, international conference speaker (SQLBits, PASS)
- SSIS Framework is a metadata-driven orchestration layer that sits on top of the SSIS Catalog
- Primary audience: SQL Server/SSIS data engineers and their managers
- Primary traffic source: Andy's LinkedIn posts and conference appearances
- Competitor landscape: dbt, Dagster, Prefect, Fivetran, Airbyte (all modern, dark-themed, well-designed)
- SSIS perceived as "legacy" -- page must subvert this perception with modern design
- SQL Server 2016 EOL July 2026 creates urgency for SSIS estate modernization
- Existing site: entdna.com (no baseline analytics data available)

## Constraints

- **Tech stack**: Static HTML + Tailwind CSS (CDN). No frameworks. No build step.
- **Tracking**: Must support both Nessus CRM (vanilla JS) AND GA4 + Clarity
- **Privacy**: All tracking behind cookie consent (GDPR EUR 150M fine precedent in 2026)
- **Pricing**: Placeholder until Andy provides actual numbers
- **Branding**: Dark theme -- Black (#000000), Green (#18a05c, #76e49e), Rose (#cd2653), Inter font
- **Hosting**: Vercel (free tier, static)
- **Performance**: Lighthouse 95+, LCP <2s, page weight <500KB

## Key Decisions

| Decision | Rationale | Outcome |
|----------|-----------|---------|
| Static HTML over Next.js/Astro | Single page; 80-100KB+ JS overhead for zero benefit; no build complexity | -- Pending |
| Tailwind CSS via CDN for MVP | Zero build step; can move to build step for production CSS purging later | -- Pending |
| Nessus CRM + GA4 + Clarity | Full tracking stack: CRM for leads, GA4 for analytics, Clarity for heatmaps | -- Pending |
| No Community Edition CTA | User unsure if SSIS Framework will have community edition | -- Pending |
| Cookie consent before tracking | GDPR/CCPA legal requirement; EUR 150M fine precedent | -- Pending |
| Problem-oriented messaging (PAS) | Evil Martians: problem-oriented storytelling converts best for devtools | -- Pending |
| Centered hero (not side-by-side) | Evil Martians: centered is dominant and more trustworthy for devtools | -- Pending |

---
*Last updated: 2026-03-03 after initial project definition*
