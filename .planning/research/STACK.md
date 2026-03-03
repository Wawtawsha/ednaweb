# Technology Stack

**Project:** EDNA SSIS Framework Landing Page
**Researched:** 2026-03-03
**Focus:** Industry-standard stack + conversion/tracking/privacy infrastructure

## Recommended Stack

The existing research recommends static HTML + Tailwind CSS. After analyzing 12 competitor sites and 2026 SaaS trends, I have a counterpoint to raise and then a revised recommendation.

### The Case For and Against Next.js

The 2026 industry research overwhelmingly names Next.js + Tailwind CSS as the dominant SaaS landing page stack. Here is why, and why EDNA should STILL use static HTML + Tailwind:

**Arguments for Next.js:**
- Industry standard in 2026 (most SaaS companies use it)
- Server-side rendering for SEO
- Image optimization built in (next/image)
- Easy Vercel deployment
- Component reuse if EDNA builds more pages later

**Arguments against Next.js for EDNA (these win):**
- This is a SINGLE landing page, not a web application
- Next.js adds 80-100KB+ of JavaScript that does nothing for static content
- Build tooling, dependency management, and framework upgrades are maintenance overhead
- A static HTML file on Vercel achieves sub-1-second load times with zero dependencies
- EDNA is an early-stage startup -- simplicity beats sophistication
- The existing EDNA research correctly identified this as over-engineering

**Verdict:** Static HTML + Tailwind CSS. The previous research was right. Industry consensus favors Next.js for companies building multi-page marketing sites with blogs, docs, and dynamic content. EDNA needs one page. HTML wins.

### Core Framework
| Technology | Version | Purpose | Why |
|------------|---------|---------|-----|
| HTML5 | N/A | Page structure | Zero overhead, maximum performance, universal compatibility |
| Tailwind CSS | 4.x (CDN for MVP, build step for production) | Styling | Industry standard for SaaS; dark mode, responsive, utility-first |

### Hosting
| Technology | Version | Purpose | Why |
|------------|---------|---------|-----|
| Vercel | N/A | Static hosting | Free tier, instant deploys, custom domains, HTTPS, CDN, already used by team |

### Analytics & Tracking (NEW)
| Technology | Version | Purpose | Why |
|------------|---------|---------|-----|
| Google Analytics 4 | Current | Page analytics, scroll depth, event tracking | Free, industry standard. Built-in scroll tracking at 90%. Custom GTM events needed for 25/50/75% thresholds. |
| Google Tag Manager | Current | Tag management, custom event triggers | Decouples tracking from code; non-developer can add/modify tracking without code changes |
| Microsoft Clarity | Current | Heatmaps, session recordings, behavior analytics | Free, no sampling limits, GDPR compliant. Microsoft product = natural trust signal for EDNA's Microsoft-ecosystem audience. Prefer over Hotjar. |

### Lead Capture & Email (NEW)
| Technology | Version | Purpose | Why |
|------------|---------|---------|-----|
| Calendly | Current | Meeting scheduling embed | Already in use on current EDNA site; proven friction-reducer for consultation booking |
| ConvertKit | Current | Newsletter / email marketing | Designed for creator-led businesses (Andy's brand). Better automation than Mailchimp. Landing page forms built-in. Free tier up to 1K subscribers. |

### Cookie Consent & Privacy (NEW)
| Technology | Version | Purpose | Why |
|------------|---------|---------|-----|
| CookieYes | Current | Cookie consent management | Geo-targeted banners (GDPR opt-in for EU, CCPA opt-out for California). Free tier available. Auto-scans cookies. Generates compliant banners with equal-prominence Accept/Reject buttons. |

### Supporting Libraries (add only when needed)
| Library | Version | Purpose | When to Use |
|---------|---------|---------|-------------|
| Alpine.js | 3.x | Minimal interactivity | Mobile menu toggle, accordion FAQ, tab switching |
| AOS | 2.x | Scroll animations | If adding scroll-triggered section reveals |

## Design System

### Color Palette

Based on competitor analysis, EDNA's existing dark theme is well-positioned. The universal accent color in data engineering is blue/purple/teal. EDNA uses green, which is distinctive. Recommendation: keep green as primary accent, add a blue-teal secondary for technical elements.

```css
/* EDNA Brand Colors - verified from entdna.com */
--edna-bg-primary: #000000;         /* Black background - matches Prefect, Airbyte */
--edna-bg-secondary: #111111;       /* Section alternation */
--edna-bg-code: #1a1a2e;           /* Code block background (new - industry pattern) */
--edna-border: #333333;             /* Borders and dividers */
--edna-text-primary: #ffffff;       /* White text */
--edna-text-secondary: #a0a0a0;    /* Muted text (slightly dimmer for hierarchy) */
--edna-accent-green: #18a05c;      /* Primary green accent (EDNA brand) */
--edna-accent-green-light: #76e49e; /* Light green for highlights */
--edna-accent-rose: #cd2653;       /* Rose/magenta accent (for warnings, emphasis) */

/* Technical credibility accent (industry-informed) */
--edna-accent-blue: #3b82f6;       /* Blue for links, secondary interactive elements */
--edna-accent-teal: #14b8a6;       /* Teal for code syntax, technical elements */

/* CTA Button Gradient (per industry pattern) */
--edna-cta-primary: linear-gradient(135deg, #18a05c, #14b8a6);
--edna-cta-hover: linear-gradient(135deg, #76e49e, #18a05c);
```

**Color rationale based on research:**
- **Black background**: Matches Airbyte, Prefect, Matillion (dark theme dominant in data engineering)
- **Green primary**: Distinctive -- no competitor uses green as primary accent (dbt=blue, Airbyte=purple, Dagster=purple, Fivetran=blue, Matillion=teal)
- **Blue-teal secondary**: Adds the "technical trust" signal. Color psychology research confirms: blue signals stability/trust in enterprise software; teal combines blue's trust with green's growth signal. This combination can boost perceived trust by up to 23% (ACS Creative study).
- **Rose for emphasis only**: Used sparingly for warnings, alerts, or the SQL Server 2016 EOL urgency section

### Typography

Based on industry research, Inter is the #1 font for SaaS/data engineering landing pages. EDNA's DELM Suite already uses Inter. Competitors using it: Dagster (Geist+Inter), Airbyte (Inconsolata for code). Recommendation: adopt Inter.

```css
/* Typography Stack */
--font-heading: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
--font-body: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
--font-code: 'JetBrains Mono', 'Fira Code', 'Consolas', monospace;

/* Scale (modular, mobile-first) */
--text-hero: clamp(2.5rem, 5vw, 4rem);     /* Hero headline */
--text-h2: clamp(1.75rem, 3vw, 2.5rem);    /* Section titles */
--text-h3: clamp(1.25rem, 2vw, 1.5rem);    /* Subsection titles */
--text-body: 1rem;                           /* Body text, 16px */
--text-small: 0.875rem;                      /* Captions, metadata */
--text-code: 0.9rem;                         /* Code blocks */
```

**Typography rationale:**
- Inter: Most popular SaaS font in 2026, excellent readability, variable font for performance
- JetBrains Mono for code: Standard for developer-facing code blocks, supports ligatures
- clamp() for fluid sizing: Modern responsive approach, eliminates breakpoint jumps

### Spacing & Layout

```css
/* Layout Constants */
--max-width: 1200px;           /* Content container max-width */
--section-padding: 5rem 1.5rem; /* Vertical padding for sections */
--card-radius: 0.75rem;        /* Rounded corners (industry: 8-16px) */
--code-radius: 0.5rem;         /* Code block corners */

/* Section rhythm */
/* Alternating bg-primary and bg-secondary for visual separation */
/* Consistent vertical padding across all sections */
```

## Analytics Implementation Guide (NEW)

### GA4 Setup

```html
<!-- Cookie consent must gate this script -->
<!-- Only load after user consents to analytics cookies -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'G-XXXXXXXXXX', {
    // Enhanced measurement auto-tracks scroll at 90%
    // Custom events for finer granularity below
  });
</script>
```

### Custom Events to Track

| Event | Trigger | Value |
|-------|---------|-------|
| `hero_cta_click` | Click on primary hero CTA | Which CTA was clicked |
| `secondary_cta_click` | Click on secondary hero CTA | Which CTA |
| `scroll_25` | Scroll to 25% | Requires GTM custom trigger |
| `scroll_50` | Scroll to 50% | Requires GTM custom trigger |
| `scroll_75` | Scroll to 75% | Requires GTM custom trigger |
| `newsletter_signup` | Newsletter form submission | Email captured |
| `calendly_click` | Calendly CTA clicked | Which section |
| `faq_expand` | FAQ accordion opened | Which question |
| `code_snippet_copy` | Code example copied | Which snippet |
| `edition_comparison_view` | Edition comparison section visible | Time in view |

### Lead Scoring Model (for future CRM integration)

| Behavior | Points | Intent Level |
|----------|--------|-------------|
| Page visit | 5 | Awareness |
| Scroll > 50% | 10 | Interest |
| Scroll > 75% | 15 | Engagement |
| Time on page > 2 min | 10 | Interest |
| FAQ section viewed | 5 | Evaluation |
| Edition comparison viewed | 15 | Consideration |
| Newsletter signup | 20 | Interest |
| Code snippet copied | 10 | Technical evaluation |
| Calendly CTA clicked | 50 | High intent |
| Consultation booked | 100 | Sales-ready |

### Microsoft Clarity Setup

```html
<!-- Also gated behind cookie consent -->
<script type="text/javascript">
  (function(c,l,a,r,i,t,y){
    c[a]=c[a]||function(){(c[a].q=c[a].q||[]).push(arguments)};
    t=l.createElement(r);t.async=1;t.src="https://www.clarity.ms/tag/"+i;
    y=l.getElementsByTagName(r)[0];y.parentNode.insertBefore(t,y);
  })(window, document, "clarity", "script", "CLARITY_PROJECT_ID");
</script>
```

## Cookie Consent Implementation (NEW)

### Architecture

```
Visitor arrives → CookieYes banner appears
  |
  ├── Accept All → Load GA4, Clarity, Calendly scripts
  ├── Reject All → Page functions without tracking (Calendly loads as essential)
  └── Customize → Granular toggle per category:
       ├── Essential (always on): page functionality, Calendly
       ├── Analytics (opt-in): GA4, Clarity
       └── Marketing (opt-in): future retargeting pixels
```

### Requirements
- Accept and Reject buttons must have EQUAL visual prominence (size, color, contrast)
- All non-essential categories default to OFF
- Banner must not block page content (bottom bar, not full-screen overlay)
- Geo-targeting: GDPR opt-in for EU visitors, CCPA opt-out for US visitors
- Consent stored for 12 months, re-prompt after expiry

## Competitor Technology Observations

| Company | Likely Stack | Theme | Load Time Feel |
|---------|-------------|-------|----------------|
| dbt Labs | Next.js + custom | Light | Fast |
| Fivetran | React-based | Light | Fast |
| Airbyte | Next.js + Rive animations | Dark | Medium (heavy animations) |
| Matillion | React + video | Dark teal | Medium (autoplay video) |
| Dagster | Next.js + Barlow/Geist fonts | Light | Fast |
| Prefect | Next.js + dark theme | Dark | Fast |
| Informatica | Enterprise CMS | Light | Medium |

**Key observation:** Airbyte's heavy Rive animations make it feel slower. Prefect's clean dark theme feels fastest. EDNA should prioritize Prefect's approach: clean dark theme, purposeful motion, fast loads.

## Performance Targets

| Metric | Target | Why |
|--------|--------|-----|
| Lighthouse Performance | 95+ | Each second of delay reduces conversions by 7% |
| First Contentful Paint | <1.0s | Static HTML achieves this easily |
| Largest Contentful Paint | <2.0s | Hero image/code block must render fast |
| Cumulative Layout Shift | <0.1 | No content jumping during load |
| Total page weight | <300KB | Static HTML + Tailwind CDN + fonts |
| Time to Interactive | <1.5s | CTAs must be clickable immediately |

## Alternatives Considered

| Category | Recommended | Alternative | Why Not Alternative |
|----------|-------------|-------------|---------------------|
| Framework | Static HTML + Tailwind | Next.js | Single page; 100KB+ JS overhead for zero benefit; maintenance burden |
| Framework | Static HTML + Tailwind | Astro | Better than Next.js for static, but still adds build complexity for one page |
| CSS | Tailwind CSS 4.x | Bootstrap | Bootstrap fights custom dark themes; Tailwind is industry standard |
| CSS | Tailwind CSS 4.x | Hand-written CSS | Tailwind faster to iterate, responsive utilities, dark mode built in |
| Hosting | Vercel | Netlify | Both work; Vercel already in team toolchain |
| Analytics | GA4 + Clarity | Mixpanel/Amplitude | Overkill for a landing page. These are product analytics tools. |
| Heatmaps | Microsoft Clarity | Hotjar | Clarity is free with no limits. Microsoft alignment with EDNA audience. |
| Email | ConvertKit | Mailchimp | ConvertKit built for creator-led businesses; fits Andy's brand better |
| Cookie Consent | CookieYes | Osano/OneTrust | CookieYes has good free tier, auto-scanning, and geo-targeting |
| Font | Inter | System fonts | Inter is free, adds brand consistency, matches competitor quality |
| Code font | JetBrains Mono | Fira Code | Both excellent; JetBrains Mono slightly more readable at small sizes |

## Installation

```bash
# MVP approach (Tailwind CDN - zero build step):
# Just add to HTML <head>:
# <script src="https://cdn.tailwindcss.com"></script>
# <link rel="preconnect" href="https://fonts.googleapis.com">
# <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">

# Production approach (build step for smaller CSS):
npm init -y
npm install -D tailwindcss @tailwindcss/cli
npx tailwindcss init
# Configure purge paths, build optimized CSS
```

## Sources

### Competitor Analysis (WebFetch, 2026-03-03)
- dbt Labs, Fivetran, Airbyte, Matillion, Dagster, Prefect, Informatica, IBM StreamSets

### Analytics & Tracking
- [GA4 Scroll Tracking](https://www.analyticsmania.com/post/scroll-tracking-with-google-analytics-4-and-google-tag-manager/)
- [Semrush: Scroll Depth in GA4](https://www.semrush.com/blog/google-analytics-scroll-depth/)
- [ZoomInfo: Visitor Tracking Tools 2026](https://pipeline.zoominfo.com/marketing/website-visitor-tracking-tools)

### Privacy & Compliance
- [SecurePrivacy: Cookie Consent Implementation 2026](https://secureprivacy.ai/blog/cookie-consent-implementation)
- [SecurePrivacy: Cookie Banner Design 2026](https://secureprivacy.ai/blog/cookie-banner-design-2026)
- [CookieYes: CPRA Cookie Consent](https://www.cookieyes.com/blog/cpra-cookie-consent/)

### Color & Typography Research
- [Color Combinations for Landing Pages](https://www.landingpageflow.com/post/best-color-combinations-for-better-landing-pages)
- [Color Psychology in Web Design](https://www.qcfixer.com/2026/02/26/color-psychology-in-web-design/)
- [ACS Creative: Color Psychology in B2B](https://www.acscreative.com/insights/the-psychology-behind-color-in-b2b-branding-what-actually-converts/)
- [Most Popular Fonts for Landing Pages](https://saaslandingpage.com/articles/the-15-most-popular-fonts-for-landing-pages/)

### Design Trend Research
- [SaaS Landing Page Trends 2026](https://www.saasframe.io/blog/10-saas-landing-page-trends-for-2026-with-real-examples)
- [Evil Martians: 100 Devtool Landing Pages](https://evilmartians.com/chronicles/we-studied-100-devtool-landing-pages-here-is-what-actually-works-in-2025)
