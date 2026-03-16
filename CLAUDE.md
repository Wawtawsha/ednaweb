# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

# EDNA SSIS Framework Landing Page

## Project Overview

Conversion-optimized landing page for **EDNA** (Enterprise Data & Analytics), showcasing the **SSIS Framework** product — a metadata-driven orchestration engine for SQL Server Integration Services.

- **Owner**: Andy Leonard — 8-time Microsoft Data Platform MVP, Chief Data Engineer at EDNA
- **Repo**: `Wawtawsha/ednaweb` (GitHub)
- **Live URL**: https://ednaweb.vercel.app
- **Hosting**: Vercel (static deployment, no build step)

## Tech Stack

- **Static HTML** — single `index.html` file (~1500 lines), no framework
- **Tailwind CSS** via CDN (`cdn.tailwindcss.com`) — no build step, no PostCSS
- **Google Fonts** — Inter (body/headings), JetBrains Mono (code blocks)
- **Vanilla JavaScript** — no dependencies, no npm, no node_modules
- **Vercel** — static hosting, deploy with `vercel --prod --yes`

The Tailwind CDN console warning is expected and harmless in dev/production. If you need to eliminate it, switch to a Tailwind build step.

## File Structure

```
ednaweb/
  index.html          # Main landing page (all 13 sections + tracking + forms)
  privacy.html        # Privacy policy page (GDPR/CCPA)
  CLAUDE.md           # This file — project standards for Claude Code
  .gitignore          # Excludes images, node_modules, .vercel, playwright artifacts
  .planning/          # GSD planning docs (roadmap, requirements, research, state)
    STATE.md          # Current project state + all placeholder tracking
    ROADMAP.md        # 3-phase roadmap (all complete)
    REQUIREMENTS.md   # 27 v1 requirements
    PROJECT.md        # Project definition
    research/         # 5 research files (~1400 lines of competitive/UX analysis)
```

## EDNA Brand Standards

### Colors
| Name | Hex | Usage |
|------|-----|-------|
| Black | `#000000` | Page background |
| Dark | `#0a0a0a` | Alternate section background |
| Surface | `#1a1a1a` | Cards, inputs, code blocks |
| Border | `#2a2a2a` | All borders |
| Muted | `#888888` | Secondary text |
| Green | `#18a05c` | Primary brand, CTAs, links, accents |
| Green Light | `#76e49e` | Hover states, secondary green |
| Green Glow | `rgba(24, 160, 92, 0.15)` | Button hover shadow |
| Rose | `#cd2653` | Error states, problem/pain emphasis |
| Rose Light | `#e85d7f` | Hover on rose elements |

### Typography
- **Headings/Body**: Inter (weights: 400, 500, 600, 700, 800)
- **Code blocks**: JetBrains Mono (weights: 400, 500, 600)
- **Hero size**: `clamp(2.25rem, 5vw, 4rem)`
- **Section headings**: `clamp(1.75rem, 3.5vw, 2.75rem)`
- **Max page width**: 1200px

### Tone
- Professional, authoritative, conversational (Andy Leonard's voice)
- NOT salesy — educational authority, narrative-driven
- Problem-Agitation-Solution (PAS) copy framework
- Andy's tagline: "I Am Here To Help."

## Page Sections (in order)

1. **Navigation** — Sticky, transparent->blurred on scroll, mobile hamburger
2. **Hero** — "The SSIS Catalog Was Never Finished." + code snippet + dual CTAs
3. **Trust Strip** — 5 stats: 20+ years, 12+ books, 8x MVP, 100+ conferences, 1M+ packages
4. **Problem** — PAS framework, Andy's quote, 3 pain point cards
5. **Solution** — Before/after code comparison
6. **Features** — 4 chess-layout blocks (alternating text/visual)
7. **DILM Suite** — 6 product ecosystem cards
8. **Pricing** — 3-tier (Standard/Professional/Enterprise) — PLACEHOLDER prices
9. **About Andy** — Bio, credentials, Engineer of Data link, photo PLACEHOLDER
10. **Testimonials** — 3 cards (1 real paraphrase, 2 PLACEHOLDER)
11. **Newsletter** — Inline email form + Substack fallback
12. **FAQ** — 6-item accordion
13. **Contact** — Contact form (left) + Calendly booking (right)
14. **Footer** — 4-column: brand, products, resources, connect

## Tracking Infrastructure

All tracking is gated behind a cookie consent banner (GDPR/CCPA compliant).

### Cookie Consent
- Fixed bottom banner with equal Accept/Reject buttons
- Consent stored in `localStorage` as JSON with 365-day expiry
- Key: `edna_cookie_consent` — values: `accepted`, `rejected`
- Rejected = zero scripts loaded, full page functionality

### Three Tracking Services
All configured in the `CONFIG` object at line ~1395 of index.html:

1. **GA4** — Dynamic script injection, scroll depth events at 25/50/75/90%
2. **Microsoft Clarity** — Standard snippet, dynamically injected
3. **Nessus CRM** — Custom vanilla JS tracking (ported from React hook):
   - Session ID (per browser session, `sessionStorage`)
   - Page views, CTA clicks, scroll depth, time-on-page, section visibility
   - Endpoint: `https://rjudjhjcfivugbyztnce.supabase.co/functions/v1/track-visitor`

### Lead Capture Forms
Both forms POST to Nessus CRM submit-lead endpoint:
- **Newsletter form** (`#newsletter-form`) — email only, source: `newsletter`
- **Contact form** (`#contact-form`) — name, email, company, source: `contact_form`
- Endpoint: `https://rjudjhjcfivugbyztnce.supabase.co/functions/v1/submit-lead`
- In placeholder mode (default), forms simulate success without making network requests

## Placeholders (Must Be Replaced Before Production)

### Tracking IDs
- `window.EDNA_NESSUS_CLIENT_ID` — shared global in `<script>` block before all others (single source of truth for both tracking and lead forms)
- `GA4_ID: 'G-XXXXXXXXXX'` — in CONFIG object inside tracking IIFE
- `CLARITY_ID: 'xxxxxxxxxx'` — in CONFIG object inside tracking IIFE

### URLs
- **Domain**: `ssisframework.com` in canonical/OG meta (lines 15, 21) — confirm actual domain
- **OG image**: `ssisframework.com/assets/images/og-image.png` (lines 22, 29) — file doesn't exist yet
- **Terms of Service**: `#` placeholder (line ~1178) — needs a real page or removal
- **Slack**: `dilmsuite.slack.com` (line ~1120) — confirm URL

### Content
- **Pricing**: All 3 tiers say "Contact Us / for pricing" (lines ~696, ~734, ~769)
- **Testimonials 2 & 3**: Fabricated quotes with generic titles (lines ~877-907)
- **Andy's photo**: Emoji placeholder (line ~811) — needs actual headshot

### Confirmed Real URLs
- Calendly: `https://calendly.com/andy-leonard/meet-with-us`
- Substack: `https://engineerofdata.substack.com`
- Blog: `https://andyleonard.blog`
- LinkedIn: `https://linkedin.com/in/andyleonard`
- X/Twitter: `https://x.com/andyleonard`
- DILM Suite: `https://dilmsuite.com`
- DELM Suite: `https://delmsuite.com`
- EDNA main site: `https://entdna.com`
- Contact email: `info@entdna.com`

## Development

**No build step, no linter, no test suite.** This is a static site — just HTML files served directly.

### Local Development
```bash
npx http-server -p 8787 -c-1
# Open http://localhost:8787
```

### Deploy to Vercel
```bash
vercel --prod --yes
```
Vercel project: `shrike-medias-projects/ednaweb`

### Git
- Remote: `https://github.com/Wawtawsha/ednaweb.git`
- Single branch: `main`
- Git user: `Wawtawsha` / `231076215+Wawtawsha@users.noreply.github.com`

## Code Patterns

### CSS
- Tailwind utility classes for everything except: scroll reveal, nav transition, FAQ accordion, code highlighting, focus styles, btn-primary glow — those are in `<style>` block
- `.reveal` + `.visible` classes for scroll-triggered animations via IntersectionObserver
- `prefers-reduced-motion: reduce` respected (disables all animations)
- All custom colors defined in `tailwind.config.theme.extend.colors.edna`

### JavaScript
- All JS is inline in `<script>` tags at bottom of body
- No modules, no imports, no bundling
- Three script blocks:
  1. UI interactions (mobile menu, sticky nav, scroll reveal, FAQ accordion)
  2. Form handlers (newsletter + contact, with shared `submitLead()` helper)
  3. Cookie consent + tracking IIFE (self-contained, runs last)

### Accessibility
- Skip-to-content link
- `aria-expanded` on menu/FAQ toggles
- `role="dialog"` on cookie banner
- `sr-only` labels on form inputs
- `focus-visible` green outline on all interactive elements
- `:target` scroll offset for fixed nav
- WCAG 2.1 AA focus indicators

## Planning Docs

The `.planning/` directory contains the full GSD (Get Stuff Done) planning system:
- `STATE.md` — Current state, all placeholder tracking, phase deliverables
- `ROADMAP.md` — 3-phase roadmap (all phases complete)
- `REQUIREMENTS.md` — 27 original requirements mapped to implementations
- `research/` — Competitive analysis, UX patterns, architecture decisions, pitfalls

These docs provide full context on every decision made during development.
