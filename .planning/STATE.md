# Project State

## Project Reference

See: .planning/ROADMAP.md (updated 2026-03-03)
See: .planning/REQUIREMENTS.md (updated 2026-03-03)

**Core value:** Convert SSIS professionals into SSIS Framework customers through a modern, conversion-optimized landing page that amplifies Andy Leonard's credibility
**Current focus:** Phase 2 - Privacy + Tracking

## Current Position

Phase: 2 of 3 (Privacy + Tracking)
Plan: 0 of 2 in current phase
Status: Ready to plan Phase 2
Last activity: 2026-03-03 -- Phase 1 complete (all 4 plans)

Progress: [████░░░░░░] 40%

## Performance Metrics

**Velocity:**
- Total plans completed: 4
- Average duration: ~15 min
- Total execution time: ~1 hour

**By Phase:**

| Phase | Plans | Total | Avg/Plan |
|-------|-------|-------|----------|
| Phase 1: Visual Page | 4/4 | ~1 hr | ~15 min |

**Recent Trend:**
- Last 5 plans: 01-01, 01-02, 01-03, 01-04
- Trend: All completed in single session

*Updated after each plan completion*

## Phase 1 Deliverables

### Files Created
- `index.html` - Complete landing page (all 13 sections, ~1180 lines)
- `privacy.html` - Privacy policy page (~130 lines)

### What's Built
1. Sticky nav with EDNA branding + mobile hamburger menu
2. Centered hero: "The SSIS Catalog Was Never Finished." + code snippet + dual CTAs
3. Trust strip: 5-column grid (20+ years, 12+ books, MVP, 100+ conferences, 1000s packages)
4. Problem section: PAS framework with Andy's quote + 3 pain point cards
5. Solution section: Before/after code comparison (500+ lines T-SQL vs 2 lines)
6. Features: 4 chess-layout blocks (orchestration, cross-project, restartability, governance)
7. DILM Suite: 6 product cards (Framework, Catalog Compare, Framework Manager, Browser, Training, DELM)
8. Pricing: 3-tier comparison (Standard/Professional/Enterprise) with "Contact Us" placeholders
9. About Andy: Bio, credentials, "I Am Here To Help" quote, photo placeholder
10. Testimonials: 3 cards (1 paraphrased real, 2 placeholder)
11. Newsletter: Substack link with topic tags
12. FAQ: 6-item accordion (properly collapsed by default)
13. Final CTA + footer

### Design System
- EDNA brand colors (black, green #18a05c/#76e49e, rose #cd2653)
- Inter + JetBrains Mono fonts via Google Fonts
- Tailwind CSS CDN with custom config
- Dark theme, scroll reveal animations, reduced motion support
- SVG inline favicon

### SEO/Accessibility
- Complete OG + Twitter Card meta tags
- JSON-LD SoftwareApplication schema
- Canonical URL, robots meta
- Skip-to-content link, aria attributes
- Focus-visible styles (green outline)
- Scroll-margin-top for fixed nav offset
- WCAG 2.1 AA focus indicators

## Accumulated Context

### Decisions

- [Roadmap]: Static HTML + Tailwind CSS (CDN), no frameworks, no build step
- [Roadmap]: Nessus CRM integration (vanilla JS) AND GA4 + Clarity for tracking
- [Roadmap]: No Community Edition CTA -- user unsure if it will exist
- [Roadmap]: Pricing placeholders ready for Andy Leonard's actual numbers
- [Roadmap]: Cookie consent required BEFORE any tracking (GDPR/CCPA)
- [User Decision]: Product is AVAILABLE NOW for purchase -- build buy-now CTAs
- [User Decision]: Full product showcase -- SSIS Framework hero + DILM Suite ecosystem
- [Research]: Catalog Compare Enterprise = $4,995/year (publicly priced)
- [Research]: Training: SSIS Premium $199/yr, Premium Level $749/yr, Azure QuickStart $24.99/mo
- [Research]: Andy's voice = conversational, narrative-driven, educational authority, NOT salesy
- [Research]: Engineer of Data newsletter on Substack (paid model) + DILM Suite Slack channel
- [Research]: SSIS Framework has Community + Commercial editions; Commercial includes Standard/Professional/Enterprise tiers
- [Phase 1]: Canonical URL set to ssisframework.com (placeholder -- needs actual domain)
- [Phase 1]: Tailwind CDN warning is expected and harmless for dev; will use build step for production if needed

### Pending Todos

- Vercel deployment (deferred -- page is ready to deploy, needs domain decision)

### Blockers/Concerns

- Pricing: Need actual pricing from Andy Leonard for edition comparison table
- Testimonials: Need real customer quotes with specifics (name, title, company, quantified results)
- Logo/photo assets: Need EDNA logo (SVG), Andy's photo (WebP), OG preview image
- Nessus CRM: Need EDNA client_id (Phase 2 blocker)
- Newsletter backend: Currently links to Substack; Phase 3 may add inline form
- Domain: Need to decide on domain (ssisframework.com? dilmsuite.com/ssis-framework?)

## Session Continuity

Last session: 2026-03-03
Stopped at: Phase 1 complete; ready to plan Phase 2 (cookie consent + tracking)
Resume file: None
