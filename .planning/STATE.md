# Project State

## Project Reference

See: .planning/ROADMAP.md (updated 2026-03-03)
See: .planning/REQUIREMENTS.md (updated 2026-03-03)

**Core value:** Convert SSIS professionals into SSIS Framework customers through a modern, conversion-optimized landing page that amplifies Andy Leonard's credibility
**Current focus:** ALL PHASES COMPLETE -- Ready for content + deployment

## Current Position

Phase: 3 of 3 (Lead Capture + Integrations) -- COMPLETE
Plan: 2 of 2 in current phase
Status: All 3 phases complete (8 plans total)
Last activity: 2026-03-03 -- Phase 3 complete (all 2 plans)

Progress: [██████████] 100%

## Performance Metrics

**Velocity:**
- Total plans completed: 8
- Average duration: ~10 min
- Total execution time: ~1.5 hours

**By Phase:**

| Phase | Plans | Total | Avg/Plan |
|-------|-------|-------|----------|
| Phase 1: Visual Page | 4/4 | ~1 hr | ~15 min |
| Phase 2: Privacy + Tracking | 2/2 | ~15 min | ~8 min |
| Phase 3: Lead Capture + Integrations | 2/2 | ~15 min | ~8 min |

**Recent Trend:**
- All 8 plans: 01-01, 01-02, 01-03, 01-04, 02-01, 02-02, 03-01, 03-02
- Trend: All completed in single session

*Updated after each plan completion*

## Phase 1 Deliverables

### Files Created
- `index.html` - Complete landing page (all 13 sections, ~1550 lines)
- `privacy.html` - Privacy policy page (~150 lines)

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
11. Newsletter: Inline email capture form with Substack fallback
12. FAQ: 6-item accordion (properly collapsed by default)
13. Contact section: Contact form + Calendly booking + email/Slack links
14. Footer: 4-column grid (brand, products, resources, connect)

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

## Phase 2 Deliverables

### Cookie Consent Banner (PRIV-01)
- Fixed bottom bar, non-blocking, equal-prominence Accept/Reject buttons
- `role="dialog"` with `aria-label` and `aria-describedby`
- Consent stored in localStorage with 365-day expiry
- Returns visitors: no re-prompt (consent persists)
- Rejected: zero tracking scripts loaded, full page functionality
- Privacy Policy link in banner text

### Tracking Scripts (TRCK-01, TRCK-02, TRCK-03)
All gated behind cookie consent -- scripts only load after "Accept":

- **GA4**: Dynamic script injection, custom scroll depth events at 25/50/75/90%
- **Microsoft Clarity**: Standard snippet, dynamically injected
- **Nessus CRM** (vanilla JS port from Shrike):
  - Session ID (per browser session, `sessionStorage`)
  - Page view tracking
  - CTA click tracking (all `#contact`, `calendly`, `.btn-primary` links)
  - Scroll depth at 25/50/75/90%
  - Time-on-page (fires on `visibilitychange` to hidden)
  - Section visibility tracking (IntersectionObserver, 30% threshold)
  - Silent failure on all fetches (`keepalive: true`, `.catch(() => {})`)

### Placeholder IDs (need real values)
- `GA4_ID: 'G-XXXXXXXXXX'`
- `CLARITY_ID: 'xxxxxxxxxx'`
- `NESSUS_CLIENT_ID: '00000000-0000-0000-0000-000000000000'`

All three skip initialization when placeholder IDs are detected.

## Phase 3 Deliverables

### Newsletter Form (LEAD-01)
- Inline email capture form replacing Substack link
- Client-side email validation
- POST to Nessus CRM `/functions/v1/submit-lead` endpoint
- Success/error feedback messages
- Substack fallback link below form
- Placeholder mode: simulates success when client ID is placeholder

### Contact Form (LEAD-02, LEAD-03)
- 3-field form: Name (required), Email (required), Company (optional)
- Client-side validation (name presence, email format)
- POST to Nessus CRM `/functions/v1/submit-lead` endpoint
- Success/error feedback messages
- Button state management (disabled + "Sending..." during submission)

### Calendly Integration (INTG-01)
- "Schedule on Calendly" button with calendar SVG icon
- Links to `https://calendly.com/entdna` (PLACEHOLDER -- needs actual Calendly URL)
- Styled as primary CTA in right column

### Contact Section Layout
- Two-column layout on desktop, stacked on mobile
- Left: Contact form ("Send Us a Message")
- Right: Calendly booking + email + Slack community links

### Shared Form Infrastructure
- `submitLead()` helper function for Nessus CRM endpoint
- `isValidEmail()` regex validation
- `showMsg()` helper for success/error feedback styling
- Placeholder mode: all forms simulate success when `LEAD_CLIENT_ID` is placeholder

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

## Remaining Work (Content + Deployment)

### Placeholder IDs (need real values before go-live)
- `GA4_ID: 'G-XXXXXXXXXX'` -- Replace with real GA4 Measurement ID
- `CLARITY_ID: 'xxxxxxxxxx'` -- Replace with real Microsoft Clarity project ID
- `NESSUS_CLIENT_ID: '00000000-0000-0000-0000-000000000000'` -- Replace with EDNA's Nessus CRM client ID
- `LEAD_CLIENT_ID` -- Same as NESSUS_CLIENT_ID (appears in form handler section)

### Content Placeholders
- Pricing: Need actual pricing from Andy Leonard for Standard/Professional/Enterprise tiers
- Testimonials: 2 of 3 are placeholder -- need real customer quotes (name, title, company, quantified result)
- About photo: Emoji placeholder -- need Andy's actual photo (WebP recommended)
- OG image: `og-image.png` referenced but doesn't exist -- need social preview image
- Calendly URL: `calendly.com/entdna` is placeholder -- need actual Calendly scheduling link

### Deployment (DEPL-01)
- Domain: Need to decide (ssisframework.com? dilmsuite.com/ssis-framework?)
- Vercel: Page is ready to deploy as static site
- Performance target: sub-2s LCP, Lighthouse 95+, <500KB total weight

## Session Continuity

Last session: 2026-03-03
Stopped at: All 3 phases complete; page is functionally done
Resume file: None
Next: Replace placeholder content with real values, then deploy to Vercel
