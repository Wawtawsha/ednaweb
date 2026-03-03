# Architecture Patterns: Landing Page Layout

**Domain:** Data engineering tool landing page
**Researched:** 2026-03-03
**Focus:** Page architecture patterns from competitor analysis, industry research, + analytics/tracking/privacy infrastructure

## Recommended Page Architecture

Based on analysis of 12 data engineering competitors and the Evil Martians 100-devtool study, here is the recommended section flow with the design pattern behind each section.

```
┌──────────────────────────────────────────────────────────┐
│  [Optional] Eyebrow Banner                               │
│  "SQL Server 2016 EOL: July 2026"                        │
│  bg: accent gradient, full-width, dismissible             │
├──────────────────────────────────────────────────────────┤
│  Navigation Bar (sticky on scroll)                        │
│  Logo | Problem | Solution | Features | About | [CTA]    │
│  bg: transparent initially, bg-primary on scroll          │
├──────────────────────────────────────────────────────────┤
│  HERO SECTION                                             │
│  ┌──────────────────────────────────────────────────┐    │
│  │  Centered headline (problem-oriented)             │    │
│  │  Centered subtitle (solution-oriented)            │    │
│  │  [Primary CTA]  [Secondary CTA]                   │    │
│  │                                                    │    │
│  │  ┌──────────────────────────────────────────┐     │    │
│  │  │  Syntax-highlighted code block            │     │    │
│  │  │  exec custom.execute_catalog_parent_pkg   │     │    │
│  │  │  @application_name = 'My Application'     │     │    │
│  │  └──────────────────────────────────────────┘     │    │
│  └──────────────────────────────────────────────────┘    │
│  bg: bg-primary (#000000)                                 │
├──────────────────────────────────────────────────────────┤
│  TRUST STRIP                                              │
│  Logo wall (if available) or metric strip                 │
│  "X years | Y stars | Z packages | MVP"                  │
│  bg: bg-secondary (#111111), border-top/bottom            │
├──────────────────────────────────────────────────────────┤
│  PROBLEM SECTION                                          │
│  "The SSIS Catalog Was Never Finished"                    │
│  Pain points + Andy's quotes                              │
│  Optional: diagram of catalog gaps                        │
│  bg: bg-primary (#000000)                                 │
├──────────────────────────────────────────────────────────┤
│  SOLUTION SECTION                                         │
│  Before/After comparison                                  │
│  Manual orchestration vs. Framework                       │
│  Code example with syntax highlighting                    │
│  bg: bg-secondary (#111111)                               │
├──────────────────────────────────────────────────────────┤
│  FEATURES (Chess Layout)                                  │
│  ┌────────────────┬────────────────┐                     │
│  │ Text (problem) │ Visual/code    │  Feature 1          │
│  ├────────────────┼────────────────┤                     │
│  │ Visual/code    │ Text (problem) │  Feature 2          │
│  ├────────────────┼────────────────┤                     │
│  │ Text (problem) │ Visual/code    │  Feature 3          │
│  └────────────────┴────────────────┘                     │
│  bg: bg-primary (#000000)                                 │
├──────────────────────────────────────────────────────────┤
│  "YOU MIGHT NEED THIS IF..." CHECKLIST                    │
│  Checkbox-style criteria list                             │
│  bg: bg-secondary (#111111)                               │
├──────────────────────────────────────────────────────────┤
│  EDITION COMPARISON TABLE                                 │
│  Community | Commercial | Enterprise                      │
│  Feature checkmarks per edition                           │
│  CTA per column                                           │
│  bg: bg-primary (#000000)                                 │
├──────────────────────────────────────────────────────────┤
│  CREDIBILITY / ABOUT SECTION                              │
│  Andy Leonard bio card + credentials                      │
│  Optional: testimonial quotes                             │
│  bg: bg-secondary (#111111)                               │
├──────────────────────────────────────────────────────────┤
│  NEWSLETTER / LEAD CAPTURE (NEW)                          │
│  "Join X data engineers"                                  │
│  Value preview: past newsletter topics                    │
│  Email-only form (ConvertKit)                             │
│  Optional: lead magnet download                           │
│  bg: bg-primary (#000000)                                 │
├──────────────────────────────────────────────────────────┤
│  FAQ SECTION (NEW)                                        │
│  6-8 questions, accordion format                          │
│  ROI, timelines, Community vs Commercial, migration       │
│  bg: bg-secondary (#111111)                               │
├──────────────────────────────────────────────────────────┤
│  FINAL CTA BLOCK                                          │
│  Full-width, visually distinct                            │
│  "Ready to stop managing packages one at a time?"         │
│  [Schedule a Demo]  [Try Community Edition]               │
│  bg: gradient (green -> teal) or accent-colored           │
├──────────────────────────────────────────────────────────┤
│  FOOTER                                                   │
│  EDNA logo | Links | Social | Copyright                   │
│  Privacy Policy | Terms of Service                        │
│  bg: bg-primary (#000000), border-top                     │
└──────────────────────────────────────────────────────────┘

OVERLAY: Cookie Consent Banner (bottom bar, non-blocking)
OVERLAY: Sticky Header CTA (always visible)
```

## Component Boundaries

| Component | Responsibility | Design Pattern Source |
|-----------|---------------|---------------------|
| Eyebrow Banner | Urgency/timeliness signal | Evil Martians: "eyebrow" pattern creates momentum |
| Navigation | Wayfinding + persistent CTA | Industry standard: sticky nav with CTA button |
| Hero | First impression, value proposition | Centered hero (Evil Martians: dominant pattern) |
| Trust Strip | Credibility below fold | Universal: every competitor has logos or metrics here |
| Problem | Pain recognition | PAS framework (Problem-Agitation-Solution) |
| Solution | Relief + proof | Before/after + code snippet |
| Features | Capability detail | Chess layout (Evil Martians: alternating pattern) |
| Checklist | Self-qualification | Andy's blog post criteria; drives "yes, that's me" response |
| Editions | Decision support | Standard SaaS comparison table |
| Credibility | Trust building | Founder bio + credentials (early-stage pattern) |
| Newsletter | Lead capture (low friction) | Email-only form, value preview, progressive profiling |
| FAQ | Objection handling + analytics | Accordion format; track which questions opened |
| Final CTA | Conversion safety net | Evil Martians: full-width, distinct, single goal |
| Cookie Consent | Privacy compliance | Bottom bar, geo-targeted, gates all tracking |
| Footer | Utility links + legal | Standard |

## Analytics & Tracking Architecture (NEW)

### Data Flow: Visitor Journey

```
Visitor arrives
    |
    v
Cookie consent banner appears (bottom bar, non-blocking)
    |
    ├── Accept All → Initialize tracking stack:
    │   ├── GA4 (page view, scroll depth at 25/50/75/90%)
    │   ├── Microsoft Clarity (heatmaps, session recordings)
    │   └── Google Tag Manager (custom event triggers)
    │
    ├── Reject All → Page functions fully without tracking
    │   └── Calendly still loads (classified as "essential" functionality)
    │
    └── Customize → Granular toggles:
        ├── Essential (always on): page functionality, Calendly
        ├── Analytics (opt-in): GA4, Clarity
        └── Marketing (opt-in): future retargeting pixels

User interaction → Event capture (only if analytics consent given)
    |
    ├── Scroll events:
    │   ├── 25% depth → ga4_event('scroll_25')
    │   ├── 50% depth → ga4_event('scroll_50')  -- "genuine interest" threshold
    │   ├── 75% depth → ga4_event('scroll_75')
    │   └── 90% depth → ga4_event('scroll_90')  -- GA4 built-in
    │
    ├── CTA clicks:
    │   ├── Hero primary CTA → ga4_event('hero_cta_primary')
    │   ├── Hero secondary CTA → ga4_event('hero_cta_secondary')
    │   ├── Sticky nav CTA → ga4_event('nav_cta_click')
    │   ├── Final CTA → ga4_event('final_cta_click')
    │   └── Edition-specific CTA → ga4_event('edition_cta', {edition: 'community|commercial|enterprise'})
    │
    ├── Content engagement:
    │   ├── FAQ question opened → ga4_event('faq_expand', {question: 'which question'})
    │   ├── Code snippet copied → ga4_event('code_copy')
    │   ├── Section time-in-view → Clarity session recording
    │   └── Edition comparison viewed → ga4_event('editions_viewed')
    │
    └── Conversions:
        ├── Newsletter signup → ga4_event('newsletter_signup') + ConvertKit API
        ├── Calendly click → ga4_event('calendly_click', {section: 'hero|final'})
        ├── Calendly booked → ga4_event('consultation_booked')  -- via Calendly webhook
        └── GitHub download → ga4_event('community_download')
```

### Lead Scoring Model (Future CRM Integration)

```
Lead Score = sum of behavioral signals

+5   Page visit
+10  Scroll > 50% (genuine interest)
+15  Scroll > 75% (deep engagement)
+10  Time on page > 2 minutes
+5   FAQ section viewed
+15  Edition comparison viewed (evaluation stage)
+20  Newsletter signup
+10  Code snippet copied (technical evaluation)
+50  Calendly CTA clicked (high intent)
+100 Consultation booked (sales-ready)
-20  Bounced in < 10 seconds (wrong audience)

Thresholds:
0-20:   Awareness (no action)
21-50:  Interest (add to newsletter nurture)
51-80:  Consideration (flag for Andy to review)
81+:    Sales-ready (prioritize follow-up)
```

### Cookie Consent Architecture

```
┌─────────────────────────────────────────────────────┐
│  CookieYes Script (loads first, before any tracking) │
│                                                       │
│  1. Detect visitor geolocation                        │
│  2. Serve appropriate banner:                         │
│     EU/UK → GDPR opt-in (must accept before tracking) │
│     California → CCPA opt-out (can track, must offer opt-out) │
│     Other US → Track with banner notification          │
│  3. Store consent in cookie (12-month expiry)          │
│  4. Fire consent event to GTM dataLayer                │
│  5. GTM triggers load GA4, Clarity only if consented   │
└─────────────────────────────────────────────────────┘

Banner Requirements (2026 enforcement):
- Accept and Reject buttons: EQUAL prominence (size, color, position)
- All non-essential categories: DEFAULT OFF
- No pre-selected checkboxes
- Clear language (no jargon like "legitimate interest processing")
- Does NOT block page content (bottom bar, not full-screen)
- Includes "Customize" option for granular control
```

## File Structure

```
ednaweb/
  index.html              # Single-page landing page
  privacy.html            # Privacy policy (required for cookie consent)
  assets/
    images/
      edna-logo.svg       # EDNA logo (vector for crisp rendering)
      edna-logo-light.svg # Light version for dark backgrounds
      hero-code.png       # Fallback for code block if needed
      andy-leonard.webp    # Andy's photo (WebP, compressed)
      og-image.png        # Open Graph preview image (1200x630)
      favicon.ico         # Favicon
    screenshots/           # If Framework Manager UI screenshots added
  .planning/              # Planning and research docs
  README.md               # Deployment instructions (if needed)
```

## Patterns to Follow

### Pattern 1: Centered Hero with Code Visual
**What:** Bold centered headline, subtitle, dual CTAs, code block below
**Evidence:** Evil Martians study: "In the vast majority of examples studied, the hero section is centered: a big, bold headline in the middle of the screen, with a supporting graphical element placed right below."
**Best for:** SSIS Framework -- the product's elegance IS the one-line stored procedure call
**Implementation:**
```html
<section class="min-h-screen flex flex-col items-center justify-center text-center px-6">
  <h1 class="text-5xl md:text-7xl font-bold tracking-tight max-w-4xl">
    The SSIS Catalog Was Never Finished
  </h1>
  <p class="text-xl text-gray-400 mt-6 max-w-2xl">
    SSIS Framework completes the picture. One stored procedure.
    One argument. Every package executes in order.
  </p>
  <div class="flex gap-4 mt-8">
    <a class="bg-green-600 text-white px-8 py-3 rounded-lg font-semibold">Schedule a Demo</a>
    <a class="border border-gray-600 text-gray-300 px-8 py-3 rounded-lg">Try Community Edition</a>
  </div>
  <!-- Code snippet visual below -->
  <div class="mt-12 bg-[#1a1a2e] rounded-xl p-8 text-left font-mono max-w-2xl w-full">
    <span class="text-gray-500">-- Execute 71 SSIS packages with one command</span><br>
    <span class="text-green-400">exec</span> custom.execute_catalog_parent_package<br>
    &nbsp;&nbsp;<span class="text-rose-400">@application_name</span> = <span class="text-yellow-300">'Framework Test'</span>
  </div>
</section>
```

### Pattern 2: Problem-Agitation-Solution (PAS) Narrative Flow
**What:** Lead with recognized pain, amplify it, present solution
**Evidence:** Evil Martians ranked problem-oriented storytelling as most engaging feature block approach. All B2B SaaS research confirms PAS for landing pages.
**Implementation:** Problem section uses Andy's own quotes (authenticity > marketing copy). Solution section shows the before/after code comparison.

### Pattern 3: Chess Layout for Features
**What:** Alternating text-left/visual-right then text-right/visual-left for feature blocks
**Evidence:** Evil Martians: "Adds rhythm without complexity." Used by Dust and others.
**Implementation:**
```html
<!-- Feature 1: text left, visual right -->
<div class="grid md:grid-cols-2 gap-12 items-center">
  <div>
    <h3>Stop Managing Packages One at a Time</h3>
    <p>The SSIS Catalog lets you deploy packages...</p>
  </div>
  <div class="bg-[#1a1a2e] rounded-xl p-6">
    <!-- code or screenshot -->
  </div>
</div>

<!-- Feature 2: visual left, text right -->
<div class="grid md:grid-cols-2 gap-12 items-center">
  <div class="bg-[#1a1a2e] rounded-xl p-6 md:order-first">
    <!-- code or screenshot -->
  </div>
  <div>
    <h3>Metadata, Not Code</h3>
    <p>Add packages by adding metadata rows...</p>
  </div>
</div>
```

### Pattern 4: Sticky Nav with CTA
**What:** Navigation bar that sticks to top on scroll, with primary CTA button always visible
**Evidence:** Industry standard (Prefect, Airbyte, Matillion all do this). Conversion research: keeping CTA visible during scroll prevents dropout.
**Implementation:**
```html
<nav class="fixed top-0 w-full z-50 bg-black/80 backdrop-blur-sm border-b border-gray-800">
  <div class="max-w-6xl mx-auto flex justify-between items-center py-4 px-6">
    <a href="#" class="text-xl font-bold text-green-400">EDNA</a>
    <div class="hidden md:flex gap-8 items-center">
      <a href="#problem" class="text-gray-400 hover:text-white">Problem</a>
      <a href="#solution" class="text-gray-400 hover:text-white">Solution</a>
      <a href="#features" class="text-gray-400 hover:text-white">Features</a>
      <a href="#about" class="text-gray-400 hover:text-white">About</a>
      <a href="#contact" class="bg-green-600 text-white px-4 py-2 rounded-lg text-sm font-semibold">Schedule a Demo</a>
    </div>
  </div>
</nav>
```

### Pattern 5: Full-Width Final CTA with Visual Distinction
**What:** Final section with distinct background, motivating copy, and single clear action
**Evidence:** Evil Martians: "Visually distinct: Separate background. Scale: Full-width, prominent positioning. Message: Short, motivating copy. Button: Single goal focus."
**Implementation:** Use EDNA green gradient background to make this section visually pop against the dark page.

### Pattern 6: Progressive Disclosure with Scroll Tracking (NEW)
**What:** Content reveals as visitor scrolls; each scroll depth milestone tracked for lead scoring
**Evidence:** GA4 built-in tracks 90% scroll. Custom events at 25/50/75% identify engagement levels. Time on hero >30s = genuine interest.
**Implementation:**
```html
<!-- Intersection Observer for scroll tracking -->
<script>
  // Only runs if analytics consent given
  if (window.analyticsConsented) {
    const thresholds = [0.25, 0.5, 0.75];
    const observer = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          gtag('event', 'section_view', {
            section_id: entry.target.id,
            scroll_depth: entry.intersectionRatio
          });
        }
      });
    }, { threshold: thresholds });

    document.querySelectorAll('section[id]').forEach(s => observer.observe(s));
  }
</script>
```

### Pattern 7: Newsletter Signup with Value Preview (NEW)
**What:** Show what the newsletter contains before asking for email. Inline form, not popup.
**Evidence:** Newsletter signups with value demonstration convert 3-5x better than generic "subscribe." Progressive profiling (email only first) achieves 35% better lead qualification.
**Implementation:**
```html
<section id="newsletter" class="py-20 px-6">
  <div class="max-w-2xl mx-auto text-center">
    <h2 class="text-3xl font-bold">Engineer of Data Newsletter</h2>
    <p class="text-gray-400 mt-4">Join data engineers who read about:</p>
    <div class="flex flex-wrap gap-3 justify-center mt-4">
      <span class="bg-gray-800 px-3 py-1 rounded-full text-sm">SSIS to Fabric Migration</span>
      <span class="bg-gray-800 px-3 py-1 rounded-full text-sm">ADF Performance Patterns</span>
      <span class="bg-gray-800 px-3 py-1 rounded-full text-sm">Biml Best Practices</span>
    </div>
    <form class="mt-8 flex gap-3 max-w-md mx-auto">
      <input type="email" placeholder="your@email.com"
        class="flex-1 bg-gray-900 border border-gray-700 rounded-lg px-4 py-3 text-white">
      <button type="submit"
        class="bg-green-600 text-white px-6 py-3 rounded-lg font-semibold whitespace-nowrap">
        Subscribe
      </button>
    </form>
  </div>
</section>
```

## Anti-Patterns to Avoid

### Anti-Pattern 1: Feature-List Storytelling
**What:** Leading feature blocks with feature names ("Orchestration," "Governance," "Logging")
**Why bad:** Evil Martians ranked this lowest: "Simple 'here's what we have' -- fails to connect features to user needs"
**Instead:** Problem-oriented headlines: "Stop Managing Packages One at a Time" not "Orchestration"

### Anti-Pattern 2: Isolated Testimonial Block
**What:** Putting all testimonials in one section at the bottom
**Why bad:** Evil Martians found contextual placement near features outperforms isolated blocks
**Instead:** Place relevant testimonials adjacent to the features they validate

### Anti-Pattern 3: SPA Framework for Static Content
**What:** Using React/Next.js/Vue for one page
**Why bad:** 80-100KB+ JavaScript for zero interactive benefit; maintenance overhead; slower initial load
**Instead:** Static HTML + Tailwind CSS + optional Alpine.js (15KB if interactivity needed)

### Anti-Pattern 4: Side-by-Side Hero Layout
**What:** Text on left, visual on right in the hero
**Why bad:** Evil Martians: "Classic SaaS feel; harder to execute in dev tool space." Centered is dominant.
**Instead:** Centered hero with visual below headline

### Anti-Pattern 5: Heavy Decorative Animations
**What:** Rive canvases, Lottie animations, 3D Spline embeds
**Why bad:** Airbyte's approach feels heavier than Prefect's clean approach; increases load time; data engineers prefer substance
**Instead:** Micro-animations with purpose: scroll reveals, hover state transitions, code block highlight animations. Subtle illuminating borders on CTA buttons can boost CTR by 15%.

### Anti-Pattern 6: Cookie Wall (Full-Screen Consent) (NEW)
**What:** Blocking all page content behind a full-screen cookie consent overlay
**Why bad:** Massive bounce rate increase. Legally questionable. Hostile UX.
**Instead:** Non-intrusive bottom bar with clear Accept/Reject buttons. Page fully visible behind banner.

### Anti-Pattern 7: Tracking Before Consent (NEW)
**What:** Loading GA4, Clarity, and other tracking scripts before cookie consent
**Why bad:** GDPR violation. Fines up to EUR 150M (SHEIN precedent, 2026). UK ICO systematically reviewing websites.
**Instead:** Gate ALL third-party scripts behind CookieYes consent manager. Only load after explicit consent.

## Performance Targets

| Metric | Target | How to Achieve |
|--------|--------|---------------|
| First Contentful Paint | < 1.0s | Static HTML, no framework JS, system font fallback |
| Largest Contentful Paint | < 1.5s | Hero is text+code (not image), font preloading |
| Total Blocking Time | < 100ms | No heavy JavaScript, minimal third-party scripts |
| Cumulative Layout Shift | < 0.05 | Fixed dimensions on all images, font-display: swap |
| Page weight | < 500KB total | Tailwind purge, WebP images, no framework bundle |
| Lighthouse Performance | 95+ | All above combined |

## Responsive Breakpoints

| Breakpoint | Layout Changes |
|-----------|---------------|
| < 640px (mobile) | Single column, hamburger nav, stacked CTAs, smaller hero text |
| 640-1024px (tablet) | Two-column features begin, full nav visible |
| > 1024px (desktop) | Full layout, max-width container, generous whitespace |

Note: 68% of B2B buyers research on mobile. Design mobile-FIRST, not mobile-as-afterthought.

## SEO Architecture

```html
<!-- Essential meta tags -->
<meta name="description" content="SSIS Framework: Metadata-driven orchestration for SQL Server Integration Services. Execute hundreds of SSIS packages with a single stored procedure call.">
<meta name="keywords" content="SSIS Framework, SSIS orchestration, SSIS Catalog, data integration, ETL framework, SSIS management, Enterprise Data Analytics">

<!-- Open Graph (critical for LinkedIn sharing -- primary traffic source for EDNA audience) -->
<meta property="og:title" content="EDNA SSIS Framework - Complete Your SSIS Catalog">
<meta property="og:description" content="Metadata-driven orchestration for SSIS. One stored procedure. One argument. Every package executes in order.">
<meta property="og:image" content="assets/images/og-image.png">
<meta property="og:type" content="website">

<!-- Twitter Card -->
<meta name="twitter:card" content="summary_large_image">

<!-- Structured Data -->
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "SoftwareApplication",
  "name": "SSIS Framework",
  "description": "Metadata-driven orchestration framework for SQL Server Integration Services",
  "applicationCategory": "DeveloperApplication",
  "operatingSystem": "Windows",
  "offers": {
    "@type": "Offer",
    "price": "0",
    "priceCurrency": "USD",
    "description": "Community Edition - Free and Open Source"
  }
}
</script>
```

## Scalability Considerations (NEW)

| Concern | At 100 visitors/month | At 10K visitors/month | At 100K visitors/month |
|---------|----------------------|----------------------|------------------------|
| Hosting | Vercel free tier, static HTML | Vercel free tier still works | Vercel Pro ($20/mo) for bandwidth |
| Analytics | GA4 free tier sufficient | GA4 + Clarity heatmaps | Consider segment-based analysis |
| Email | ConvertKit free (up to 1K subs) | ConvertKit Creator ($29/mo) | ConvertKit Creator Pro |
| Performance | No concerns | CDN handles load | Ensure image optimization |
| Lead Management | Email inbox | HubSpot free CRM | HubSpot paid or Salesforce |
| A/B Testing | Manual variant deployment | Vercel Edge Config | Full experimentation platform |

## Sources

- [Evil Martians: 100 Devtool Landing Pages](https://evilmartians.com/chronicles/we-studied-100-devtool-landing-pages-here-is-what-actually-works-in-2025)
- [SaaS Landing Page Trends 2026](https://www.saasframe.io/blog/10-saas-landing-page-trends-for-2026-with-real-examples)
- [B2B SaaS Websites 2026](https://www.vezadigital.com/post/best-b2b-saas-websites-2026)
- [GA4 Scroll Tracking](https://www.analyticsmania.com/post/scroll-tracking-with-google-analytics-4-and-google-tag-manager/)
- [SecurePrivacy: Cookie Consent 2026](https://secureprivacy.ai/blog/cookie-consent-implementation)
- [SecurePrivacy: Cookie Banner Design 2026](https://secureprivacy.ai/blog/cookie-banner-design-2026)
- [Genesys Growth: B2B SaaS Landing Pages 2026](https://genesysgrowth.com/blog/designing-b2b-saas-landing-pages)
- Competitor analysis of 12 data engineering landing pages (WebFetch, 2026-03-03)
