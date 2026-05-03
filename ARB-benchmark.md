# AdSense Readiness Benchmark (ARB)

> ARB v4.0 positions the framework as a broader publisher monetization readiness system, while keeping AdSense as the primary policy baseline and scoring contract.

> **6 pillars × 13-20 items = 105 evaluation criteria**, with a fixed **core 79 review set** for baseline readiness checks and 26 extension items for deeper or site-type-specific review.

---

## How to Read This Document

| Depth | Sections | You Will Learn |
|-------|----------|----------------|
| Skim | Parts 1–2 | What ARB is + the core 79 set + all 105 items at a glance |
| Apply | Parts 3–4 | How to score a site, weight by type, and run the review workflow |
| Master | Part 5 | Detailed Pass/Partial/Fail criteria for every item with examples |
| Operate | Part 6 + `skills/README.md` | How to package results and run the current skills-based workflow |

---

# Part 1: Framework Overview

## What is ARB?

ARB (AdSense Readiness Benchmark) is a structured checklist for evaluating whether a website can pass Google AdSense review and maintain ongoing compliance. In v4.0, it also acts as the scoring backbone for broader publisher monetization planning, including multi-network readiness, benchmark comparison, and approval probability estimation. It maps directly to the three Google policy documents that govern AdSense:

| Policy Source | Coverage | ARB Pillars |
|---------------|----------|-------------|
| [Google Publisher Policies](https://support.google.com/adsense/answer/10502938) | Content & behavior rules | CI, PC, SI |
| [AdSense Content & UX Guide](https://support.google.com/adsense/answer/10015918) | Content quality & navigation | CI, UX |
| [Google Search Spam Policies](https://developers.google.com/search/docs/essentials/spam-policies) | Spam and deceptive practices | SI, PC |

## Stage Tags

Every check item carries a stage tag indicating when it matters most:

| Tag | When It Matters |
|-----|----------------|
| `Pre` | Before submitting AdSense application |
| `Active` | After approval, ongoing compliance |
| `Both` | Applies at all stages |

## 6 Pillars

| Code | Pillar | Core Question | Items |
|------|--------|---------------|-------|
| **CI** | Content Integrity | Is the content original, sufficient, structured, and genuinely useful? | 18 |
| **PC** | Policy Compliance | Does the site avoid all prohibited content categories and protect user data? | 13 |
| **TH** | Technical Health | Is the site technically sound, fast, secure, and properly marked up? | 20 |
| **UX** | User Experience | Is the site accessible, navigable, readable, and ad-friendly for all users? | 18 |
| **TD** | Trust & Disclosure | Is the site transparent, credible, and properly disclosing relationships? | 20 |
| **SI** | Search Integrity | Does the site use only legitimate SEO and content practices? | 16 |
| | **Total** | | **105** |

## Core 79 Review Set

ARB v4.0 keeps all 105 criteria as the source of truth. For baseline readiness triage, use the fixed core 79 set carried forward from the original framework.

| Pillar | Core IDs | Core Count |
|--------|----------|------------|
| **CI** | CI01-CI14 | 14 |
| **PC** | PC01-PC11 | 11 |
| **TH** | TH01-TH13 | 13 |
| **UX** | UX01-UX15 | 15 |
| **TD** | TD01-TD14 | 14 |
| **SI** | SI01-SI12 | 12 |
| | **Total** | **79** |

The remaining 26 items are extension items used for deeper audits, active-state checks, or site-type-specific review. If an audit brief does not define a custom extension profile, score all 105 items.

| Pillar | Extension IDs | Count |
|--------|---------------|-------|
| **CI** | CI15-CI18 | 4 |
| **PC** | PC12-PC13 | 2 |
| **TH** | TH14-TH20 | 7 |
| **UX** | UX16-UX18 | 3 |
| **TD** | TD15-TD20 | 6 |
| **SI** | SI13-SI16 | 4 |
| | **Total** | **26** |

## Site-Type Extension Profiles

Use the mixed model below when you do not want to score all 105 items by default:

1. Always score the fixed core 79 set.
2. Add the recommended extension profile for the primary site type.
3. Add any triggered extension items from the conditional rules table.
4. If a site clearly spans multiple business models, use the union of the relevant extension profiles or fall back to all 105 items.

These profiles are defaults, not caps. Reviewers may add more extension items when the risk surface is wider than the nominal site type.

| Site Type | Recommended Extension Items | Why These Items Matter Most |
|-----------|-----------------------------|-----------------------------|
| **Blog / Content** | CI15, CI17, CI18, TH14, TH17, TH18, UX17, TD15, TD16, SI13, SI15 | Freshness, citations, media completeness, and operational quality often decide whether editorial sites look maintained and trustworthy |
| **Tool / SaaS** | CI18, TH14, TH15, TH16, TH17, TH18, TH19, TH20, UX17, UX18, TD17, TD20, SI15, SI16 | Tools are judged heavily on reliability, performance, error handling, entity trust, and international/compliance depth |
| **Affiliate** | CI17, CI18, PC12, PC13, TD15, TD16, TD20, SI13, SI14, SI15, SI16 | Affiliate sites need stronger disclosure-adjacent controls, fresher claims, outbound link hygiene, and higher trust signals |
| **News / Aggregator** | CI15, CI17, CI18, TH14, TH17, TH18, UX16, UX17, UX18, TD15, TD16, SI13, SI15, SI16 | News-like properties need freshness, pagination quality, citation discipline, and stronger anti-spam/link-quality controls |
| **E-commerce** | CI17, CI18, PC12, PC13, TH14, TH15, TH17, TH18, TH19, TH20, UX16, UX17, UX18, TD17, TD18, TD19, TD20, SI13, SI14, SI15, SI16 | Commerce sites need refund/service terms, business verification, operational reliability, richer UX handling, and stricter monetization/link compliance |
| **Forum / Community** | CI18, PC12, PC13, TH14, TH15, TH17, TH18, TH20, UX16, UX17, UX18, TD16, TD20, SI13, SI14, SI15, SI16 | Community sites carry higher moderation, pagination, UGC-link, and operational-risk surfaces that the core 79 alone does not cover |

## Conditional Extension Triggers

Apply these extension items even if they are not in the default site-type profile.

| Condition | Add These Items |
|-----------|-----------------|
| Site is already monetized with AdSense units or auto-ads | PC12, PC13 |
| Site operates in more than one language or geo-market | UX18, TD20 |
| Site sells products, subscriptions, bookings, or paid services | TD17, TD18, TD19 |
| Site relies heavily on video, audio, or image-led content | CI18, TH19 |
| Site has significant pagination, archives, or feed-style browsing | UX16, SI15 |
| Site has meaningful outbound commercial, sponsored, or affiliate linking | SI13, SI14 |
| Site has meaningful uptime/SLA expectations or user workflows | TH15, TH16, UX17 |

## MECE Boundaries

| If the issue is about… | Pillar |
|----------------------|--------|
| What content says / how much exists / content structure / metadata | CI |
| Whether content is forbidden by policy / user data protection | PC |
| Server, SSL, speed, crawlability, schema markup, security headers | TH |
| Page layout, navigation, ad placement, accessibility, mobile usability | UX |
| Legal pages, ownership identity, disclosures, author credibility | TD |
| SEO manipulation, spam techniques, internal linking quality | SI |

---

# Part 2: Complete 105-Item Checklist

> One-line standard for every item. Use the core 79 set above for baseline triage and this section for full-scope review.

### CI — Content Integrity (18 Items)

| ID | Check Item | Stage | One-Line Standard |
|----|-----------|-------|-------------------|
| CI01 | Minimum Content Volume | Pre | Each page has ≥300 words of original body text |
| CI02 | Content Originality | Both | No paragraphs copy-pasted from other sites verbatim |
| CI03 | Topic Depth | Pre | Content goes beyond a dictionary definition; provides actionable detail |
| CI04 | Supported Language | Pre | Site's primary language is in Google's supported language list |
| CI05 | Content Freshness | Active | High-value pages updated within the past 12 months |
| CI06 | No Thin Pages at Scale | Both | <10% of indexed pages are under 200 words |
| CI07 | No Self-Duplicate Content | Both | Same long-form text does not repeat across multiple pages |
| CI08 | AI Content Has Added Value | Both | If AI-generated, each page offers unique facts, data, or perspective |
| CI09 | Content Serves Users, Not Bots | Both | Content is written for human readers, not search engine keyword insertion |
| CI10 | No Scraped Media Aggregation | Both | Embedded third-party videos/images have original commentary adding value |
| CI11 | Meta Description Quality | Pre | Each page has a unique meta description between 120-158 characters |
| CI12 | Title Tag Optimization | Pre | Each page has a unique title tag (50-60 chars) with primary keyword near the start |
| CI13 | Heading Hierarchy | Both | Proper H1-H6 structure with exactly one H1 per page and logical heading order |
| CI14 | Content Structure Signals | Both | Content uses lists, tables, bullet points, and formatting to enhance readability |
| CI15 | Content Update Frequency | Both | High-value content categories show regular updates (at least quarterly for evergreen topics) |
| CI16 | Content Consistency Across Pages | Both | Information on the same topic is consistent across different pages; no contradictions |
| CI17 | Data Freshness in Claims | Both | Statistical claims cite sources within 2 years; outdated data is marked as historical |
| CI18 | Multimedia Content Quality | Both | Video/audio content has transcripts, captions, or text summaries; embedded media loads properly |

### PC — Policy Compliance (13 Items)

| ID | Check Item | Stage | One-Line Standard |
|----|-----------|-------|-------------------|
| PC01 | No Illegal Content | Both | No content promoting illegal acts, counterfeit goods, or IP infringement |
| PC02 | No Dangerous / Hateful Content | Both | No content inciting hatred, threats, or targeted harassment |
| PC03 | No Explicit Sexual Content | Both | No adult content unless operating under an AdSense adult content agreement |
| PC04 | No Deceptive / Misleading Claims | Both | No false health, financial, or electoral claims contradicting scientific consensus |
| PC05 | No Harmful Health Misinformation | Both | No anti-vaccine, COVID-denial, or conversion therapy content |
| PC06 | No Facilitation of Dishonesty | Both | No guides on hacking, credential forgery, or academic dishonesty |
| PC07 | No Malware or Unwanted Software | Both | No downloads that install software without clear user consent |
| PC08 | No Animal Abuse Promotion | Both | No content promoting dogfighting, wildlife trafficking, or endangered species sales |
| PC09 | Regulated Content Properly Handled | Both | Gambling/tobacco/alcohol content complies with applicable AdSense restricted category rules |
| PC10 | Affiliate Disclosure Present ⚠️ VETO | Both | Any page with affiliate links has a clearly visible disclosure statement |
| PC11 | User Data Rights Available | Both | Users can request data deletion/export; privacy policy explains how |
| PC12 | Ad Unit Quantity Compliance | Active | No more than 3 ad units per page (excluding auto-ads) per AdSense policy |
| PC13 | Ad Code Placement Verification | Active | AdSense code placed in `<head>` or before closing `</body>`; no code in comments or broken script tags |

### TH — Technical Health (20 Items)

| ID | Check Item | Stage | One-Line Standard |
|----|-----------|-------|-------------------|
| TH01 | HTTPS Enabled Site-Wide ⚠️ VETO | Pre | All pages served over HTTPS; HTTP redirects to HTTPS |
| TH02 | SSL Certificate Valid | Both | SSL cert not expired; valid for the domain; no mixed-content warnings |
| TH03 | robots.txt Not Blocking Key Pages | Both | robots.txt exists and does not Disallow: / for Googlebot |
| TH04 | XML Sitemap Present | Pre | sitemap.xml exists at root or declared in robots.txt |
| TH05 | ads.txt Present (if applicable) | Both | ads.txt file present if site uses programmatic ad networks |
| TH06 | Acceptable Page Load Speed | Both | Homepage loads in <3s on a standard connection (LCP < 2.5s) |
| TH07 | Mobile-Responsive Design | Both | Viewport meta tag present; layout renders correctly on mobile |
| TH08 | No Major Broken Links | Both | Homepage and top-level pages have no 404 responses in primary navigation |
| TH09 | Canonical Tags Consistent | Both | Self-referencing canonical tags present on all major pages |
| TH10 | Ad Code Correctly Implemented | Active | AdSense auto-ads or ad unit code present; no code errors in browser console |
| TH11 | Core Web Vitals - FID | Both | First Input Delay <100ms on mobile (field data via CrUX) |
| TH12 | Core Web Vitals - CLS | Both | Cumulative Layout Shift <0.1 on mobile (field data via CrUX) |
| TH13 | Structured Data/Schema Markup | Pre | Relevant schema types (Article, Product, Review, etc.) implemented without errors |
| TH14 | Custom 404 Page Quality | Both | Custom 404 page exists with navigation links; not just "404 Not Found" server default |
| TH15 | Server Uptime Monitoring | Both | Site has uptime monitoring or shows >99% uptime over past 30 days (if verifiable) |
| TH16 | DNS Resolution Speed | Both | DNS resolution completes in <200ms (tested from common geographic regions) |
| TH17 | CDN Implementation | Both | CDN or caching solution used for static assets (images, CSS, JS) |
| TH18 | Resource Compression | Both | Gzip or Brotli compression enabled for text-based resources |
| TH19 | Image Optimization | Both | Images use modern formats (WebP/AVIF) or have proper compression; lazy loading for below-fold images |
| TH20 | Third-Party Script Count | Both | Fewer than 15 third-party scripts loaded on homepage; scripts don't block rendering |

### UX — User Experience (18 Items)

| ID | Check Item | Stage | One-Line Standard |
|----|-----------|-------|-------------------|
| UX01 | Clear Site Navigation | Pre | A menu or nav bar links to main categories; visible on all pages |
| UX02 | Content-to-Ad Ratio Acceptable | Active | Ads occupy <30% of visible viewport; content is dominant |
| UX03 | No Intrusive Interstitials | Both | No full-screen pop-ups on page load that block reading |
| UX04 | Readable Typography and Layout | Pre | Body text ≥14px; sufficient line-height; content not crammed |
| UX05 | Internal Links Form Logical Paths | Both | Every page is ≤3 clicks from the homepage; no orphan pages |
| UX06 | No Deceptive UI Elements | Both | No fake download buttons, fake "close" X icons, or misleading CTAs |
| UX07 | Cross-Browser Compatibility | Pre | Site renders correctly in Chrome, Firefox, and Safari |
| UX08 | Ad Placement Does Not Interfere | Active | Ads are not placed directly adjacent to navigation buttons or interactive elements |
| UX09 | No Return-Button Hijacking | Both | Browser back button navigates to expected previous page |
| UX10 | Functional Search / Filtering | Pre | If site has >30 pages, a search box or category filter is present |
| UX11 | Color Contrast WCAG AA | Pre | Text has contrast ratio ≥4.5:1 (normal) or ≥3:1 (large text) against background |
| UX12 | Image Alt Text Present | Both | All informative images have descriptive alt text; decorative images use alt="" |
| UX13 | Touch Target Size | Pre | All touch targets (buttons, links) are ≥48×48px on mobile devices |
| UX14 | Text Resizes to 200% | Pre | Page remains readable and functional when browser text zoomed to 200% |
| UX15 | Keyboard Navigation Works | Pre | All interactive elements accessible via Tab key; visible focus indicators |
| UX16 | Content Pagination Quality | Both | Paginated content has rel="next/prev" tags; clear navigation; each page has sufficient content |
| UX17 | Custom Error Pages (5xx) | Both | Custom error pages exist for 500/503 errors with helpful navigation or contact options |
| UX18 | Multi-language Site Handling | Both | If multi-language, proper hreflang tags implemented; language switcher visible and functional |

### TD — Trust & Disclosure (20 Items)

| ID | Check Item | Stage | One-Line Standard |
|----|-----------|-------|-------------------|
| TD01 | Privacy Policy Present ⚠️ VETO | Pre | A privacy policy page exists and is linked from every page footer |
| TD02 | Contact Information Present | Pre | At least one contact method (email, form, or address) is publicly visible |
| TD03 | About Page Present | Pre | An "About" or equivalent page describes the site's purpose and ownership |
| TD04 | Cookie / GDPR Consent Notice | Both | Cookie consent banner present if serving users in the EU |
| TD05 | Accurate Site Identity | Both | Site name, ownership, and country of origin are not misrepresented |
| TD06 | No Brand Impersonation | Both | Site does not imitate logos, names, or layouts of other established brands |
| TD07 | Terms of Service Present | Active | A ToS page exists describing user rights and content policies |
| TD08 | Disclosure for Sponsored Content | Both | Sponsored or paid posts are labeled "Sponsored" or "Advertisement" |
| TD09 | Author / Editor Bylines | Both | Article authors are identified; YMYL-adjacent content has credential signals |
| TD10 | COPPA Compliance (if applicable) | Both | If site targets under-13s, appropriate COPPA measures are in place |
| TD11 | Author Credentials Verifiable | Both | Author bios link to credentials (LinkedIn, publications, certifications) for YMYL topics |
| TD12 | Editorial Standards Page | Both | Site documents its content review, fact-checking, or editorial process |
| TD13 | External References/Citations | Both | Claims cite authoritative sources; links to external sources work |
| TD14 | Site Age Consistency | Pre | Domain age ≥6 months for new sites; content publication history shows consistency |
| TD15 | E-E-A-T Deep Assessment | Both | Content demonstrates Experience (first-hand insights), Expertise (credentials/knowledge), Authoritativeness (site reputation), Trustworthiness (accuracy, transparency) — especially for YMYL topics |
| TD16 | Social Media Presence | Both | Site has active, verified social media accounts linked; presence shows consistency and engagement |
| TD17 | Business Entity Verification | Both | For business sites, entity verifiable via Google Business Profile, company registry, or Better Business Bureau listing |
| TD18 | Refund Policy (if applicable) | Both | E-commerce sites have clear refund policy with timeframes and process; linked from footer |
| TD19 | Shipping/Service Terms (if applicable) | Both | E-commerce/service sites have clear shipping terms, delivery timelines, or service-level agreements |
| TD20 | GDPR Compliance Depth | Both | Privacy policy specifies data retention periods, legal basis for processing, DPO contact if required |

### SI — Search Integrity (16 Items)

| ID | Check Item | Stage | One-Line Standard |
|----|-----------|-------|-------------------|
| SI01 | No Cloaking | Both | Same content returned for Googlebot and human visitors |
| SI02 | No Doorway Pages | Both | No pages existing solely as search-rank gateways with no standalone value |
| SI03 | No Keyword Stuffing | Both | Keyword density is natural; no unreadable blocks of repeated terms |
| SI04 | No Hidden Text or Links | Both | No white-on-white text, CSS off-screen text, or zero-opacity links |
| SI05 | No Deceptive Redirects | Both | HTTP redirects match content intent; mobile users get same content as desktop |
| SI06 | No Scaled Content Abuse | Both | No mass AI-generated pages providing no original value |
| SI07 | No Content Scraping | Both | Content is not systematically copied from competitor or news sites |
| SI08 | Affiliate Content Has Added Value | Both | Affiliate pages contain original reviews, ratings, or comparisons — not just product specs from merchant |
| SI09 | No User-Generated Spam | Active | Comment sections, forums, or UGC areas are moderated; no spam links |
| SI10 | No Misleading Functionality | Both | Site does not promise functionality (e.g. "free gift card generator") it does not deliver |
| SI11 | Internal Link Anchor Quality | Both | Internal links use descriptive anchor text; not "click here" or vague terms |
| SI12 | No Orphan Pages | Both | All important content pages have at least one internal link pointing to them |
| SI13 | External Link Quality | Both | External links point to authoritative, relevant sources; no links to spam or low-quality sites |
| SI14 | Nofollow Correct Usage | Both | Paid links, affiliate links, and UGC links use rel="nofollow", "sponsored", or "ugc" appropriately |
| SI15 | Redirect Chain Length | Both | No redirect chains longer than 3 hops; all redirects are 301 (permanent) where appropriate |
| SI16 | URL Structure Quality | Both | URLs are descriptive, use hyphens (not underscores), are under 100 characters, and avoid unnecessary parameters |

---

# Part 3: Scoring System

## Per-Item Scoring

| Status | Score | Meaning |
|--------|-------|---------|
| **Pass** | 10 | Fully meets criteria |
| **Partial** | 5 | Partially meets criteria |
| **Fail** | 0 | Does not meet criteria |
| **N/A** | — | Not applicable; excluded from denominator |

## Pillar and Total Scores

Each pillar: sum of applicable items × (100 / applicable item count) = 0–100.

When scoring in profile mode, `applicable items` means the union of:

1. The fixed core 79 set
2. The selected site-type extension profile
3. Any triggered extension items

Record the score mode in the final report as one of `Core 79`, `Core 79 + Profile`, or `Full 105`.

```
Pillar Score = (sum of item scores / max possible score for pillar) × 100

Total Score = Σ (Pillar Score × Pillar Weight)
```

## Site-Type Weighting

Apply the weights below based on the primary site type:

| Pillar | Blog / Content | Tool / SaaS | Affiliate | News / Aggregator | E-commerce | Forum / Community |
|--------|:-:|:-:|:-:|:-:|:-:|:-:|
| **CI** | 25% | 15% | 20% | 25% | 20% | 15% |
| **PC** | 15% | 15% | 20% | 20% | 20% | 15% |
| **TH** | 15% | 20% | 15% | 15% | 20% | 15% |
| **UX** | 15% | 20% | 15% | 15% | 20% | 20% |
| **TD** | 15% | 15% | 20% | 15% | 15% | 20% |
| **SI** | 15% | 15% | 10% | 10% | 5% | 15% |

**Example** (Blog site, all pillars scored):
```
Total = CI×0.25 + PC×0.15 + TH×0.15 + UX×0.15 + TD×0.15 + SI×0.15
```

## Grade Scale

| Score | Grade | Meaning |
|-------|-------|---------|
| 90–100 | **Ready** | High probability of AdSense approval; maintain compliance |
| 75–89 | **Minor Fixes** | 1–3 small issues to resolve before applying |
| 60–74 | **Significant Work** | Multiple issues across 2+ pillars; fix before applying |
| 40–59 | **Major Overhaul** | Foundational problems; likely rejection without significant changes |
| 0–39 | **Not Ready** | Site does not meet basic AdSense requirements |

## Approval Probability Estimate

Use this only as a statistical planning aid in final reports. It must always be labeled as an estimate and never presented as an official Google or network decision signal.

| Score | Estimate | Typical Range | Interpretation |
|-------|----------|---------------|----------------|
| 90–100 | High | 80–92% | Strong readiness if no geo, vertical, or data-quality risks remain |
| 75–89 | Medium | 55–75% | Reasonable submission case, but weak trust or policy-adjacent items may still block approval |
| 60–74 | Low | 25–50% | Multiple pillars need work before applying |
| 40–59 | Very Low | 8–22% | Foundational issues dominate |
| 0–39 | Very Low | <8% | Not submission-ready |

The estimate should be adjusted downward when any of these are present:

- Ambiguous evidence on veto-adjacent items
- Multi-language or multi-market legal gaps
- AI-generated content at scale with weak human editorial controls
- High-risk verticals such as health, finance, or regulated commerce

## Benchmark Overlays

These overlays do not replace the 105-item scoring contract. They add market context after the core score is produced.

### Industry Vertical Baselines

| Vertical | Typical Passing Range | Notes |
|----------|-----------------------|-------|
| Technology / SaaS content | 78–92 | Strong CI and TH usually matter most |
| Personal finance | 82–95 | TD and PC thresholds are materially stricter in practice |
| Health / medical | 85–98 | YMYL trust evidence and factual accuracy dominate |
| News / current events | 75–90 | Freshness, citations, and operational consistency drive outcomes |
| E-commerce / shopping | 80–93 | TD17–TD20 and PC10–PC13 often shape final readiness |

### Traffic Tier Context

| Tier | Typical Traffic | Recommended Audit Scope |
|------|-----------------|-------------------------|
| Starter | <1K monthly UV | Core 79 or Core 79 + Profile |
| Growth | 1K–50K monthly UV | Core 79 + Profile with conditional triggers |
| Scale | 50K+ monthly UV | Full 105 plus geo, benchmark, and network overlays |

## Veto Items

The following items trigger an automatic **fail gate** regardless of total score. A site cannot be "Ready" while any veto is triggered.

| Item | Trigger | Consequence |
|------|---------|-------------|
| **TH01** HTTPS | HTTP site or no redirect | Gate: cannot pass until fixed |
| **TD01** Privacy Policy | No privacy policy found | Gate: cannot pass until fixed |
| **PC10** Affiliate Disclosure | Affiliate links present without disclosure | Gate: cannot pass until fixed |
| Any **PC** item | Policy, monetization, or compliance failure detected | Gate: blocked until resolved or manually reviewed |

---

# Part 4: Quality Workflow (3 Review Gates + Reporting Gate)

```
┌──────────────────┬──────────────────────┬──────────────────────┬─────────────────────┐
│     Gate 1       │       Gate 2         │       Gate 3            │     Gate 4          │
│  Technical Check │  Content + Policy    │ Trust + UX + Disclosure│ Remediate + Report  │
├──────────────────┼──────────────────────┼──────────────────────┼─────────────────────┤
│ Run:             │ Run:                 │ Run:                 │ Run:                │
│ technical-audit  │ ads-readiness-       │ trust-credibility-   │ content-improvement-│
│                  │ assessment           │ strategy             │ blueprint           │
│                  │ content-audit        │ ux-compliance-audit  │ technical-          │
│                  │ policy-risk-scanner  │ affiliate-link-      │ remediation-guide   │
│                  │ seo-spam-detection   │ compliance           │ ux-optimization-    │
│                  │ copyright-ip-check   │                      │ roadmap             │
│                  │                      │                      │ policy-remediation- │
│                  │                      │                      │ plan                │
│                  │                      │                      │ resubmission-       │
│                  │                      │                      │ readiness-check     │
├──────────────────┼──────────────────────┼──────────────────────┼─────────────────────┤
│ Check:           │ Check:               │ Check:               │ Produces:           │
│ TH01–TH20        │ CI01–CI18            │ TD01–TD20            │ Per-pillar scores   │
│                  │ PC01–PC13            │ UX01–UX18            │ Total weighted score│
│                  │ SI01–SI16            │ PC10 / TD08 overlaps │ Grade               │
│                  │                      │                      │ TOP 5 fixes         │
│                  │                      │                      │ Veto alerts         │
├──────────────────┼──────────────────────┼──────────────────────┼─────────────────────┤
│ STOP if:         │ STOP if:             │ STOP if:             │                     │
│ TH01 fails       │ Any PC item fails    │ TD01 fails           │                     │
│ (no HTTPS)       │ (policy/compliance)  │ (no privacy policy)  │                     │
└──────────────────┴──────────────────────┴──────────────────────┴─────────────────────┘
```

The repository now includes `skills/arb-full-audit/` as the default documentation-level orchestrator. It does not yet ship executable checker scripts, so the skills remain the operative contract.


# Part 5: Detailed Criteria — All 105 Items

> Pass / Partial / Fail definitions with ❌ wrong / ✅ correct examples.

---

## CI — Content Integrity

**CI01: Minimum Content Volume** | Stage: Pre
- **Pass**: Every main content page (articles, guides, product pages) has ≥300 words of original body text
- **Partial**: Most pages meet the threshold; a few borderline pages with 150–299 words
- **Fail**: Majority of pages are under 200 words; site looks empty or placeholder-like
- ❌ "Coming soon. Check back later." (5 words total)
- ✅ 800-word article covering topic comprehensively with subheadings, examples, and a conclusion

**CI02: Content Originality** | Stage: Both
- **Pass**: Text is uniquely written for this site; no verbatim blocks copied from external sources
- **Partial**: Most content original; a few short quotes or excerpts from other sources with attribution
- **Fail**: Paragraphs are copy-pasted from Wikipedia, news sites, or competitor sites without added commentary
- ❌ Reproducing a Wikipedia article verbatim with only the page title changed
- ✅ A guide that synthesizes information from 5 sources into an original narrative with the author's own insights

**CI03: Topic Depth** | Stage: Pre
- **Pass**: Covers the topic with specifics: examples, how-to steps, data points, or nuanced analysis
- **Partial**: Surface-level treatment but with some useful details beyond a definition
- **Fail**: Content only restates the question or provides a one-paragraph dictionary definition
- ❌ "SEO stands for Search Engine Optimization. It helps websites rank on Google." (2 sentences, no detail)
- ✅ A 1,200-word guide explaining on-page factors, technical SEO, link building, and measurement — with examples for each

**CI04: Supported Language** | Stage: Pre
- **Pass**: Site's primary language is in Google's AdSense supported language list
- **Partial**: Site is bilingual; one language is supported, one is not
- **Fail**: Site's primary content is in an unsupported language
- ❌ Site written entirely in a language not listed at support.google.com/adsense/answer/9727
- ✅ English, Spanish, French, German, Japanese, or other listed supported language

**CI05: Content Freshness** | Stage: Active
- **Pass**: Top-performing and high-traffic pages show a "Last updated" date within the past 12 months
- **Partial**: Most content is recent; a few important pages have not been updated in 1–2 years
- **Fail**: Site has no visible dates; most content is clearly outdated (references years-old data as current)
- ❌ Article titled "Best AI Tools in 2021" published in 2021, never updated, still ranking
- ✅ Article shows "Updated: March 2026" and includes recent data and product changes

**CI06: No Thin Pages at Scale** | Stage: Both
- **Pass**: <10% of crawlable pages are under 200 words; thin pages are non-indexable or redirected
- **Partial**: 10–25% of pages are thin; problem is localized (e.g., tag/archive pages)
- **Fail**: >25% of pages are thin; content is broadly shallow across main content categories
- ❌ A blog with 200 posts all averaging 80 words — effectively a tagline collection
- ✅ Tag and category pages are either noindex or enriched with original intro paragraphs

**CI07: No Self-Duplicate Content** | Stage: Both
- **Pass**: Each page has a distinct focus; no large blocks of identical text appear across multiple pages
- **Partial**: Some boilerplate duplication (footer text, disclaimer) but body content is unique per page
- **Fail**: The same 500-word article appears on 10+ pages with only the title or city name swapped
- ❌ "Best Plumber in [City]" template pages that all share the same paragraph body
- ✅ Each location page has unique local details, quotes, and data

**CI08: AI Content Has Added Value** | Stage: Both
- **Pass**: AI-assisted content includes original data, first-person insights, or editorial judgment not reproducible by a generic prompt
- **Partial**: AI content is well-structured but generic; clearly paraphrasing existing information without novel contribution
- **Fail**: Mass-published AI content with no differentiation; pages are keyword-targeted filler
- ❌ 500 nearly-identical AI-generated articles on variations of "best [keyword] in [location]"
- ✅ AI-drafted article edited by a domain expert who added their own test results and commentary

**CI09: Content Serves Users, Not Bots** | Stage: Both
- **Pass**: Content reads naturally; answer flows logically; keyword usage is organic
- **Partial**: Some awkward phrasing suggesting keyword optimization, but content is still useful
- **Fail**: Text is clearly written for keyword density; reads unnaturally; user gets no value
- ❌ "Buy cheap running shoes online cheap shoes for runners best cheap shoes running"
- ✅ "If you're looking for budget-friendly running shoes, here are five options tested under $80 that held up over 200 miles."

**CI10: No Scraped Media Aggregation** | Stage: Both
- **Pass**: Embedded third-party videos or images are accompanied by original written commentary
- **Partial**: Most embeds have commentary; a few pages are video-only or image-only with minimal text
- **Fail**: Site consists primarily of embedded YouTube videos or stock image galleries with no original text
- ❌ A site that embeds 50 YouTube videos per page with only the video title as the "content"
- ✅ Embedded video is accompanied by a 400-word written summary, key timestamps, and the author's critique

**CI11: Meta Description Quality** | Stage: Pre
- **Pass**: Every page has a unique meta description between 120-158 characters that accurately summarizes the page
- **Partial**: Most pages have meta descriptions; some are too short/long or duplicated across pages
- **Fail**: No meta descriptions; or all pages use the same generic description; or descriptions are keyword-stuffed
- ❌ Meta description: "Best website for information about topics. Learn more here." (42 chars, generic)
- ✅ Meta description: "Discover 5 proven SEO strategies that increased our traffic by 340% in 6 months. Includes case study data and implementation checklist." (143 chars, specific)

**CI12: Title Tag Optimization** | Stage: Pre
- **Pass**: Each page has a unique title tag (50-60 chars) with primary keyword near the start and brand name at the end
- **Partial**: Titles exist but some are too long (>65 chars) or duplicated; keywords present but not optimally positioned
- **Fail**: Missing title tags; all pages use the same title; titles are just keywords separated by pipes
- ❌ Title: "Home | My Site" (no keywords, not descriptive)
- ✅ Title: "SEO Strategies for 2026 | Complete Guide | BrandName" (keyword-first, brand-last, proper length)

**CI13: Heading Hierarchy** | Stage: Both
- **Pass**: Exactly one H1 per page; H2-H6 used logically with no skipped levels; headings describe content structure
- **Partial**: H1 present but some heading levels skipped; or multiple H1s on same page
- **Fail**: No H1 tag; heading levels used randomly (H1 → H4 → H2); headings used for styling not structure
- ❌ Page structure: H1 → H4 → H2 → H3 → H1 (chaotic hierarchy)
- ✅ Page structure: Single H1 → H2 sections → H3 subsections → H4 details (logical hierarchy)

**CI14: Content Structure Signals** | Stage: Both
- **Pass**: Content uses varied formatting: bullet lists, numbered lists, tables, blockquotes, and bold text for emphasis
- **Partial**: Some structure present but content is mostly walls of text with minimal formatting
- **Fail**: Zero formatting; content is unbroken paragraphs with no scannable elements
- ❌ 2000-word article as 15 paragraphs with no lists, headings, or formatting
- ✅ Same article with: H2 headings, 3 bullet lists, 1 comparison table, key terms in bold, pull quote

**CI15: Content Update Frequency** | Stage: Both
- **Pass**: Core content categories (guides, reviews, resources) show updates within 3-6 months; site has regular publishing schedule
- **Partial**: Some content updated regularly; evergreen content neglected but not severely outdated
- **Fail**: No content updated in 12+ months; publication dates show long gaps with no activity
- ❌ "Best SEO Tools 2022" last updated March 2022, still on homepage as "latest"
- ✅ Category pages show "Last updated" badges; cornerstone content refreshed quarterly

**CI16: Content Consistency Across Pages** | Stage: Both
- **Pass**: Facts, figures, and advice are consistent when the same topic appears across multiple pages
- **Partial**: Minor inconsistencies (e.g., different statistics sources) but acknowledged and explained
- **Fail**: Same topic has contradictory information on different pages with no explanation
- ❌ Page A says "SEO takes 3-6 months"; Page B says "SEO takes 12-18 months" — both presented as facts
- ✅ Pages clarify conditions: "For new sites: 3-6 months" vs "For competitive keywords: 12-18 months"

**CI17: Data Freshness in Claims** | Stage: Both
- **Pass**: Statistical claims cite sources within 2 years; older data marked as historical for context
- **Partial**: Most data recent; some 2-5 year old data without historical context but still relevant
- **Fail**: Citing 2015 data as "current" without acknowledgment; statistics from defunct sources presented as current
- ❌ "According to 2020 research..." in a 2026 article, without noting if findings still hold
- ✅ "2020 research found X, and 2024 studies confirm this trend continues..."

**CI18: Multimedia Content Quality** | Stage: Both
- **Pass**: Videos have transcripts or detailed summaries; audio has show notes or transcripts; images load quickly and have context
- **Partial**: Some multimedia has text alternatives; embedded content mostly functional
- **Fail**: Critical content only in video/audio with no text alternative; broken embeds; missing alt text on informative images
- ❌ 30-minute video tutorial with no transcript, chapter markers, or summary
- ✅ Video has: full transcript, timestamped chapters, downloadable summary PDF

---

## PC — Policy Compliance

**PC01: No Illegal Content** | Stage: Both
- **Pass**: No content promoting or facilitating illegal activities, IP infringement, or counterfeit sales
- **Partial**: Ambiguous edge case (e.g., a legal gray-area topic discussed academically)
- **Fail**: Content explicitly facilitates illegal acts (piracy, drug synthesis instructions, counterfeit storefronts)

**PC02: No Dangerous / Hateful Content** | Stage: Both
- **Pass**: No content inciting hatred based on protected characteristics; no targeted harassment or threats
- **Partial**: Controversial political content without explicit incitement (borderline)
- **Fail**: Content that dehumanizes groups, calls for violence, or systematically harasses individuals

**PC03: No Explicit Sexual Content** | Stage: Both
- **Pass**: No explicit sexual text, images, audio, or video; no adult content targeting minors
- **Partial**: Mature themes discussed clinically (e.g., health site discussing STIs)
- **Fail**: Explicit pornographic content; any sexual content involving minors

**PC04: No Deceptive / Misleading Claims** | Stage: Both
- **Pass**: Claims are factually accurate; sources cited; disclaimers present for predictions
- **Partial**: Some outdated or imprecise claims, but no intentional deception
- **Fail**: Deliberate misrepresentation of facts, false endorsements, or fake credentials displayed

**PC05: No Harmful Health Misinformation** | Stage: Both
- **Pass**: Health content aligns with WHO / CDC consensus; alternative approaches noted as complementary
- **Partial**: Presents fringe views but labels them as minority positions
- **Fail**: Actively promotes anti-vaccine content, COVID-19 denial, or unproven disease cures as fact

**PC06: No Facilitation of Dishonesty** | Stage: Both
- **Pass**: No guides on bypassing authentication, creating fake documents, or academic fraud
- **Partial**: Cybersecurity content about vulnerabilities (defensive framing vs. offensive)
- **Fail**: Step-by-step guides to hack systems, forge official documents, or buy academic papers

**PC07: No Malware or Unwanted Software** | Stage: Both
- **Pass**: No downloadable files that install software without clear disclosure; no drive-by downloads
- **Partial**: Download links are present but clearly labeled with file type and size
- **Fail**: Hidden iframe injections; download buttons that trigger unexpected installs

**PC08: No Animal Abuse Promotion** | Stage: Both
- **Pass**: Animal content is educational or advocacy-based; no promotion of dogfighting, shark fins, ivory
- **Partial**: Hunting/fishing content (legal in jurisdiction, not promoting cruelty)
- **Fail**: Content advertising dogfighting events, endangered species products, or animal torture for entertainment

**PC09: Regulated Content Properly Handled** | Stage: Both
- **Pass**: Gambling/tobacco/alcohol content either absent or approved under AdSense's restricted category policy with age gates
- **Partial**: References to regulated activities in a factual/journalistic context
- **Fail**: Unlicensed online gambling promotion; targeted advertising of tobacco to minors

**PC10: Affiliate Disclosure Present** ⚠️ **VETO** | Stage: Both
- **Pass**: Clear, visible disclosure at the top of every page containing affiliate links (e.g., "This post contains affiliate links. We earn a commission at no extra cost to you.")
- **Partial**: Disclosure exists but is buried in the footer or only on an About page
- **Fail**: Affiliate links present with absolutely no disclosure anywhere on the page

**PC11: User Data Rights Available** | Stage: Both
- **Pass**: Site provides method to request data deletion/export; privacy policy describes the process; response time specified
- **Partial**: Privacy policy mentions data rights but no clear request mechanism exists
- **Fail**: No mention of user data rights; users cannot request access to or deletion of their data
- N/A if site does not collect personal data beyond analytics

**PC12: Ad Unit Quantity Compliance** | Stage: Active
- **Pass**: No more than 3 standard ad units per page (excluding auto-ads); content significantly outweighs ad units
- **Partial**: 4-5 ad units on some pages; ad density noticeable but content remains dominant
- **Fail**: 6+ ad units per page; or ads outnumber content blocks above the fold
- N/A if using only auto-ads or in pre-application stage
- ❌ Page has 7 display ad units plus 3 native ad units
- ✅ Page has 2 display units and 1 native unit; content takes 70%+ of viewport

**PC13: Ad Code Placement Verification** | Stage: Active
- **Pass**: AdSense code properly placed in `<head>` or before closing `</body>`; no code in HTML comments; no syntax errors
- **Partial**: Code present but placement suboptimal (e.g., nested deep in async-loaded content)
- **Fail**: Ad code commented out, placed in invalid locations, or malformed with syntax errors
- N/A if in pre-application stage
- ❌ `<!-- <script async src="..."></script> -->` (commented out)
- ✅ `<script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js?client=ca-pub-XXX" crossorigin="anonymous"></script>` in `<head>`

---

## TH — Technical Health

**TH01: HTTPS Enabled Site-Wide** ⚠️ **VETO** | Stage: Pre
- **Pass**: All pages return HTTPS; HTTP URLs redirect to HTTPS; no mixed-content warnings
- **Partial**: Most pages are HTTPS but some static assets (images, CSS) load over HTTP
- **Fail**: Site still runs on HTTP with no HTTPS equivalent; browser shows "Not Secure"
- ❌ `http://example.com` with no redirect
- ✅ `https://example.com` with HSTS header; all resources on HTTPS

**TH02: SSL Certificate Valid** | Stage: Both
- **Pass**: Certificate is valid, matches the domain, issued by a trusted CA, and does not expire within 30 days
- **Partial**: Certificate valid but expiring within 30 days or missing www subdomain coverage
- **Fail**: Expired certificate; self-signed certificate; certificate/domain mismatch causing browser warning

**TH03: robots.txt Not Blocking Key Pages** | Stage: Both
- **Pass**: `robots.txt` exists; Googlebot is not disallowed from main content; no `Disallow: /`
- **Partial**: Some non-essential paths blocked (e.g., `/admin/`); content pages accessible
- **Fail**: `Disallow: /` blocks all crawling; or key content directories are disallowed

**TH04: XML Sitemap Present** | Stage: Pre
- **Pass**: `sitemap.xml` accessible at root or declared in `robots.txt`; contains all main content URLs
- **Partial**: Sitemap exists but is outdated or missing recently published pages
- **Fail**: No sitemap found at any standard path; not declared in robots.txt

**TH05: ads.txt Present** | Stage: Both
- **Pass**: `ads.txt` at domain root lists Google (`google.com, pub-XXXXXXXXX, DIRECT, f08c47fec0942fa0`)
- **Partial**: ads.txt present but Google entry is incorrect or missing the verification hash
- **Fail**: Site uses programmatic ads but has no `ads.txt`; or ads.txt blocks Google entirely
- N/A if site has not yet added AdSense code

**TH06: Acceptable Page Load Speed** | Stage: Both
- **Pass**: Homepage LCP < 2.5s; total blocking time < 300ms (via Lighthouse or PageSpeed Insights)
- **Partial**: LCP 2.5–4s; performance issues present but not severely degrading experience
- **Fail**: LCP > 4s; site takes >10s to become interactive on mobile

**TH07: Mobile-Responsive Design** | Stage: Both
- **Pass**: `<meta name="viewport">` tag present; layout adapts correctly at 375px and 768px widths
- **Partial**: Viewport tag present but some elements overflow horizontally on mobile
- **Fail**: Fixed-width layout breaks on mobile; text too small to read; buttons too small to tap

**TH08: No Major Broken Links** | Stage: Both
- **Pass**: All links in the main navigation and header/footer return 200; no 404s in primary paths
- **Partial**: A few 404s exist in body content links; navigation links all work
- **Fail**: Navigation links return 404; homepage links to non-existent pages; broken internal structure

**TH09: Canonical Tags Consistent** | Stage: Both
- **Pass**: Every page has a `<link rel="canonical">` pointing to itself (or correct canonical version); no conflicting canonicals
- **Partial**: Canonical tags present on most pages but missing on some paginated or tag pages
- **Fail**: No canonical tags; or pages canonicalize to each other in a loop; or canonical points to 404

**TH10: Ad Code Correctly Implemented** | Stage: Active
- **Pass**: AdSense auto-ads script or ad units present; no JavaScript console errors related to ad code
- **Partial**: Ad code present but some units return no-fill or show errors intermittently
- **Fail**: Ad code missing; AdSense account shows "no ad serving"; code is malformed
- N/A if in pre-application stage

**TH11: Core Web Vitals - FID** | Stage: Both
- **Pass**: First Input Delay <100ms on 75%+ of mobile visits (per CrUX field data)
- **Partial**: FID 100-300ms; interactive but slight delay perceived
- **Fail**: FID >300ms; site feels sluggish or unresponsive to user input
- ❌ User taps button but nothing happens for 500ms
- ✅ Page responds to clicks/taps within 50ms consistently

**TH12: Core Web Vitals - CLS** | Stage: Both
- **Pass**: Cumulative Layout Shift <0.1 on 75%+ of mobile visits (per CrUX field data)
- **Partial**: CLS 0.1-0.25; some layout shifts but not severely disruptive
- **Fail**: CLS >0.25; content jumps significantly as page loads, causing accidental clicks
- ❌ User clicks "Read more" but button shifts up and they click an ad instead
- ✅ Page elements stay in position; no unexpected layout movement

**TH13: Structured Data/Schema Markup** | Stage: Pre
- **Pass**: Relevant schema types (Article, Product, Review, FAQ, etc.) implemented without errors; validated in Google Rich Results Test
- **Partial**: Some schema present but has errors/warnings; or only basic Organization schema
- **Fail**: No structured data; or schema has critical errors preventing rich result eligibility
- N/A for simple sites that don't benefit from rich results

**TH14: Custom 404 Page Quality** | Stage: Both
- **Pass**: Custom 404 page exists with site navigation, search option, or helpful links; returns 404 status code
- **Partial**: Custom 404 exists but is minimal (e.g., just "Page not found" with site logo)
- **Fail**: Generic server default 404 page; or 404 page soft-404s (returns 200 status)
- ❌ Apache default "Not Found. The requested URL was not found on this server."
- ✅ Custom 404 with: "Page not found. Try searching:" [search box] [link to homepage] [popular articles]

**TH15: Server Uptime Monitoring** | Stage: Both
- **Partial**: Site claims 99%+ uptime but no third-party verification; Uptime Robot or similar not linked
- **Fail**: Site frequently down; or verified uptime <95% over past month
- N/A if uptime cannot be verified (common for small sites)
- ❌ Uptime monitoring shows 47 hours of downtime in past 30 days (94% uptime)
- ✅ Public status page shows 99.8% uptime over 90 days; or site shows no downtime in manual checks over 2 weeks

**TH16: DNS Resolution Speed** | Stage: Both
- **Pass**: DNS resolves in <150ms from multiple geographic regions (measured via DNS speed test tools)
- **Partial**: DNS resolves in 150-300ms; acceptable but not optimal
- **Fail**: DNS takes >300ms to resolve; indicates slow DNS provider
- ❌ DNS lookup takes 450ms from US East, 680ms from Europe
- ✅ DNS lookup: 80ms US East, 120ms Europe, 95ms Asia Pacific

**TH17: CDN Implementation** | Stage: Both
- **Pass**: CDN or public caching (Cloudflare, AWS CloudFront, etc.) used for static assets; headers show cache hits
- **Partial**: Some caching enabled but not comprehensive; or CDN configured but cache headers missing
- **Fail**: No CDN; all assets served from origin server; high TTFB for international visitors
- ❌ All assets from `example.com/wp-content/` with no CDN subdomain
- ✅ Images/CSS/JS served from `cdn.example.com` or `*.cloudflare.com` with appropriate cache headers

**TH18: Resource Compression** | Stage: Both
- **Pass**: Gzip or Brotli compression enabled for HTML, CSS, JS; headers show `Content-Encoding: gzip` or `br`
- **Partial**: Compression enabled for some resources but not all; or compression level suboptimal
- **Fail**: No compression; text resources served uncompressed at full size
- ❌ 500KB JavaScript file served with no compression headers
- ✅ HTML file compressed to 18KB of original 85KB (Brotli encoding)

**TH19: Image Optimization** | Stage: Both
- **Pass**: Images use WebP/AVIF formats with fallbacks; file sizes appropriate for dimensions; lazy loading implemented
- **Partial**: Images optimized but in older formats (JPG/PNG); or some large images unoptimized
- **Fail**: Multiple 2MB+ images; no modern formats; no lazy loading; images significantly larger than display size
- ❌ `<img src="huge-photo.jpg" width="3000" height="2000" style="width:600px">` (serving 5MB file for 600px display)
- ✅ `<img src="photo.webp" srcset="photo-800w.webp 800w, photo-400w.webp 400w" loading="lazy">`

**TH20: Third-Party Script Count** | Stage: Both
- **Pass**: Homepage loads <10 third-party scripts; scripts have `defer` or `async` attributes; non-critical scripts loaded after interaction
- **Partial**: 10-15 third-party scripts; most non-blocking but still significant overhead
- **Fail**: 20+ third-party scripts on homepage; or scripts block rendering without async/defer
- ❌ Homepage loads 28 third-party scripts including analytics, chat widgets, social plugins, ad trackers
- ✅ Homepage loads 6 essential scripts: analytics, one chat widget, AdSense, all with async/defer

---

## UX — User Experience

**UX01: Clear Site Navigation** | Stage: Pre
- **Pass**: Persistent menu bar with clear category labels; every page shows site identity (logo/name)
- **Partial**: Navigation exists but is confusing (too many items, unclear labels, or buried)
- **Fail**: No navigation; single-page site with no links to other content; or broken menu
- ❌ Site with 50 articles but no menu, only a homepage list that goes stale
- ✅ Sticky header with: Home | Blog | About | Contact — visible on all pages

**UX02: Content-to-Ad Ratio Acceptable** | Stage: Active
- **Pass**: Ads occupy <30% of visible viewport above the fold; content is clearly dominant
- **Partial**: Ads cover 30–40% of viewport; user experience degraded but still functional
- **Fail**: Ads cover >40% of page; ads stack above content; content is secondary to ads
- N/A if in pre-application stage

**UX03: No Intrusive Interstitials** | Stage: Both
- **Pass**: No full-screen pop-up on page load; any email sign-up modals are dismissible and appear after scroll
- **Partial**: Pop-up appears but is easily dismissible and appears after 10+ seconds
- **Fail**: Full-screen interstitial blocks content on first page view; close button is hidden or deceptive

**UX04: Readable Typography and Layout** | Stage: Pre
- **Pass**: Body font ≥14px; line-height ≥1.4; sufficient contrast; paragraphs <7 lines each
- **Partial**: Readable but dense; some accessibility concerns with contrast or font size
- **Fail**: 10px gray text on white background; wall-of-text with no breaks; unreadable on mobile

**UX05: Internal Links Form Logical Paths** | Stage: Both
- **Pass**: Every page reachable in ≤3 clicks from homepage; no orphan pages
- **Partial**: Most pages reachable; a few articles buried deep or with no internal links pointing to them
- **Fail**: Many pages discoverable only via sitemap; no contextual linking between related content

**UX06: No Deceptive UI Elements** | Stage: Both
- **Pass**: All buttons and links do what they appear to do; no fake download buttons or disguised ad units
- **Partial**: Some aggressive CTA styling (red "Download" button) but not misleading
- **Fail**: Fake "Play" buttons that open ad pages; fake "Download" links that redirect to unrelated sites

**UX07: Cross-Browser Compatibility** | Stage: Pre
- **Pass**: Layout renders correctly in Chrome (latest), Firefox (latest), and Safari (latest)
- **Partial**: Minor visual differences across browsers; no functional breakage
- **Fail**: Key features non-functional in one or more major browsers; layout completely broken in Safari

**UX08: Ad Placement Does Not Interfere** | Stage: Active
- **Pass**: No ads adjacent to navigation elements, form submit buttons, or primary CTAs
- **Partial**: Ads are near interactive elements but not directly overlapping
- **Fail**: Ad units overlap navigation; clicking "Back" or "Next" frequently triggers accidental ad clicks
- N/A if in pre-application stage

**UX09: No Return-Button Hijacking** | Stage: Both
- **Pass**: Browser back button returns to the expected previous page; no history manipulation
- **Partial**: N/A — this is binary
- **Fail**: Clicking back within the site loops back to the same page; or back button triggers a download

**UX10: Functional Search / Filtering** | Stage: Pre
- **Pass**: Sites with >30 pages have a working search box or clear category/tag navigation
- **Partial**: Category pages exist but are poorly organized; no search function
- **Fail**: 100-page site with no navigation, no search, no categories — content is a flat undifferentiated list
- N/A if site has ≤30 pages

**UX11: Color Contrast WCAG AA** | Stage: Pre
- **Pass**: Text has contrast ratio ≥4.5:1 (normal text) or ≥3:1 (large text ≥18px/14pt bold) against background
- **Partial**: Most text meets contrast but some gray-on-light-gray text fails
- **Fail**: Significant content fails contrast; light gray text on white background or white text on light background
- ❌ #999999 text on #FFFFFF background (2.8:1 ratio)
- ✅ #333333 text on #FFFFFF background (12.6:1 ratio)

**UX12: Image Alt Text Present** | Stage: Both
- **Pass**: All informative images have descriptive alt text; decorative images use alt=""; charts/images with text include full text in alt
- **Partial**: Most images have alt text but some are missing or generic ("image1.png", "photo")
- **Fail**: No alt attributes on images; or critical images (charts, infographics) lack text descriptions
- ❌ `<img src="chart.png">` with no alt text describing the data
- ✅ `<img src="chart.png" alt="Bar chart showing 50% increase in Q3 2026 sales">`

**UX13: Touch Target Size** | Stage: Pre
- **Pass**: All touch targets (buttons, links, form inputs) are ≥48×48px with ≥8px spacing between targets on mobile
- **Partial**: Most targets meet size but some close-spaced buttons <48px; occasional mis-taps
- **Fail**: Multiple targets <44×44px packed closely together; difficult to tap accurately on mobile
- ❌ Three 36×36px icon buttons with 2px gaps — users tap wrong one
- ✅ 48×48px buttons with 8px spacing — easy and accurate tapping

**UX14: Text Resizes to 200%** | Stage: Pre
- **Pass**: Page remains fully readable and functional when browser text zoomed to 200%; no horizontal scroll; content doesn't overlap
- **Partial**: Mostly usable at 200% but some overflow or layout breaks
- **Fail**: Text overlaps, content cuts off, or horizontal scroll required at 200% zoom
- ❌ At 200% zoom, sidebar overlaps main content; navigation breaks
- ✅ At 200% zoom, text enlarges, layout adjusts, everything remains accessible

**UX15: Keyboard Navigation Works** | Stage: Pre
- **Pass**: All interactive elements reachable via Tab key; visible focus indicators; logical tab order; Enter/Space activate controls
- **Partial**: Keyboard works but focus indicators hard to see; tab order slightly confusing
- **Fail**: Some elements not keyboard accessible; invisible focus; Tab key trapped in component; keyboard cannot scroll or interact
- ❌ Dropdown menu opens on mouse hover but not with keyboard; no way to access links
- ✅ All menus, forms, and buttons work with Tab/Enter/Arrow keys; clear focus rings

**UX16: Content Pagination Quality** | Stage: Both
- **Pass**: Paginated content has `rel="next"` and `rel="prev"` tags; each page has ≥300 words; clear page navigation
- **Partial**: Pagination exists but missing rel tags; or some pages have thin content
- **Fail**: Infinite scroll without pagination; or paginated pages with <100 words each; broken pagination navigation
- ❌ Article split into 10 pages with 50 words per page; no rel tags; user must click "next" 10 times
- ✅ 3-page article with 600+ words per page; `<link rel="prev">` and `<link rel="next">` in `<head>`; numbered page navigation

**UX17: Custom Error Pages (5xx)** | Stage: Both
- **Pass**: Custom error pages for 500/503 with helpful message, navigation options, or contact form
- **Partial**: Custom error page exists but is minimal
- **Fail**: Generic server error pages with no branding or navigation
- ❌ "Internal Server Error" — plain text with no site identity or next steps
- ✅ Branded error page: "Something went wrong. Try our [homepage] or [contact us]"

**UX18: Multi-language Site Handling** | Stage: Both
- **Pass**: If multi-language, proper `hreflang` tags implemented; language switcher visible; no mixed-language pages
- **Partial**: `hreflang` present but some errors; or language switcher hard to find
- **Fail**: Multi-language content without `hreflang` tags; or auto-detect redirects without user consent
- N/A if single-language site
- ❌ `/es/` Spanish version has no `hreflang` pointing to it; English and Spanish content mixed on same page
- ✅ `<link rel="alternate" hreflang="es" href="https://example.com/es/article">` implemented; language switcher in header

---

## TD — Trust & Disclosure

**TD01: Privacy Policy Present** ⚠️ **VETO** | Stage: Pre
- **Pass**: Privacy policy page exists, is accessible from a footer link on every page, and covers data collection practices including third-party advertising (Google)
- **Partial**: Privacy policy exists but is not linked from every page; or content is very thin
- **Fail**: No privacy policy found anywhere on the site
- ❌ A blog with AdSense code and no privacy policy page
- ✅ `/privacy-policy` linked in footer; policy covers cookies, analytics, and advertising data

**TD02: Contact Information Present** | Stage: Pre
- **Pass**: At least one contact method visible (email address, contact form, mailing address, or social media handle with active presence)
- **Partial**: Contact form exists but email is hidden or the form is broken
- **Fail**: No contact method anywhere; no way for users or Google to reach the site owner

**TD03: About Page Present** | Stage: Pre
- **Pass**: An About page explains who runs the site, the site's purpose, and relevant expertise or background
- **Partial**: About page exists but is generic ("Welcome to my site!") with no identity information
- **Fail**: No About page; site has no identity signals other than the domain name

**TD04: Cookie / GDPR Consent Notice** | Stage: Both
- **Pass**: Cookie consent banner appears for EU users; users can accept or manage preferences; analytics fires only after consent
- **Partial**: Banner present but does not allow opt-out; or consent is not respected by scripts
- **Fail**: No cookie consent; site uses tracking cookies with no notice
- N/A if site has no EU traffic and no EU-targeting

**TD05: Accurate Site Identity** | Stage: Both
- **Pass**: Site name, author, and publisher identity are consistent and accurate across all pages
- **Partial**: Site identity present but some inconsistencies (different names on About vs. Contact)
- **Fail**: Site impersonates a different entity; or ownership is deliberately obscured

**TD06: No Brand Impersonation** | Stage: Both
- **Pass**: No use of another brand's logo, name, or trademark in a misleading way
- **Partial**: Site references competitor brands factually in comparison content
- **Fail**: Site design or name mimics a well-known brand to create confusion

**TD07: Terms of Service Present** | Stage: Active
- **Pass**: ToS page exists; covers user conduct, content ownership, and limitations of liability
- **Partial**: ToS exists but is incomplete or copied from another site unchanged
- **Fail**: No ToS page found
- N/A for personal/hobby blogs with no user-generated content

**TD08: Disclosure for Sponsored Content** | Stage: Both
- **Pass**: Every sponsored post, paid review, or advertorial is clearly labeled with "Sponsored," "Ad," or "Paid Partnership" at the top of the page
- **Partial**: Disclosure exists but appears at the bottom or in small print
- **Fail**: Paid articles appear as organic editorial content with no label

**TD09: Author / Editor Bylines** | Stage: Both
- **Pass**: Articles show author name; author has an About/bio page; YMYL-adjacent topics credit subject-matter experts
- **Partial**: Some articles have bylines; others are anonymous
- **Fail**: All content is anonymous; no editor or author identified anywhere on the site

**TD10: COPPA Compliance** | Stage: Both
- **Pass**: No behavioral advertising targeting under-13s; if site targets children, Google ad personalization is disabled
- **Partial**: Site has general audience but some child-friendly content without specific COPPA measures
- **Fail**: Site explicitly targets under-13s and runs personalized AdSense without COPPA consent mechanisms
- N/A if site content is clearly for adults only

**TD11: Author Credentials Verifiable** | Stage: Both
- **Pass**: For YMYL topics (health, finance, safety), author bios link to external verification (LinkedIn, publications, certifications, degrees)
- **Partial**: Authors have bios but credentials are self-claimed without external verification
- **Fail**: YMYL content published anonymously or under pseudonyms with no credentials; no way to verify expertise
- N/A if site covers non-YMYL topics

**TD12: Editorial Standards Page** | Stage: Both
- **Pass**: Site has a publicly accessible page describing content review process, fact-checking standards, source requirements, or editorial guidelines
- **Partial**: Some references to editorial process in About page but no dedicated standards page
- **Fail**: No mention of how content is reviewed, fact-checked, or produced
- N/A for personal blogs with single author

**TD13: External References/Citations** | Stage: Both
- **Pass**: Factual claims cite authoritative sources; links work; citations are specific (not just "sources say")
- **Partial**: Some sources cited but many claims are unsourced or link to low-quality references
- **Fail**: Significant factual claims made without sources; or most citation links are broken
- N/A for opinion/creative content

**TD14: Site Age Consistency** | Stage: Pre
- **Pass**: Domain age ≥6 months OR site shows consistent publication history with regular content over time
- **Partial**: Domain <6 months but has strong content volume and regular publishing schedule
- **Fail**: Brand new domain (<1 month) with minimal content; or site shows long gaps with no updates
- ❌ Domain registered 2 weeks ago, 3 articles, no updates since launch
- ✅ Domain registered 8 months ago, 50+ articles, content published weekly

**TD15: E-E-A-T Deep Assessment** | Stage: Both
- **Pass**: Content demonstrates all four E-E-A-T dimensions — especially for YMYL (health, finance, safety) topics
- **Partial**: E-E-A-T signals present but not comprehensive; or lacking for some YMYL content
- **Fail**: YMYL content published anonymously with no credentials, no evidence of expertise, no trustworthy sources
- N/A for non-YMYL content (entertainment, hobbies, opinion)
- ❌ Medical advice article from anonymous author, no sources, no credentials, claims contradicting consensus
- ✅ Financial guide written by CFP with 15 years experience, sources to SEC/Finra, bio links to credentials and LinkedIn

**TD16: Social Media Presence** | Stage: Both
- **Pass**: Site has active, verified social media accounts (Twitter, LinkedIn, Facebook, Instagram) with regular engagement
- **Partial**: Social accounts exist but inactive or unverified; or only one platform
- **Fail**: No social media presence; or linked accounts are suspended/broken
- N/A for personal blogs without social strategy
- ❌ Social icons link to 404 pages or accounts with 0 posts in 2 years
- ✅ Verified Twitter/X with weekly posts, LinkedIn company page with employee connections, active Instagram for visual content

**TD17: Business Entity Verification** | Stage: Both
- **Pass**: For business sites, verifiable via Google Business Profile, company registry, BBB, or Dunn & Bradstreet listing
- **Partial**: Some entity signals present (e.g., registered address) but not comprehensive
- **Fail**: Business site with no verifiable entity information; or entity information appears fabricated
- N/A for personal blogs or solo creator sites
- ❌ "About Us" lists corporate address that is actually a UPS Store mailbox; no business registration found
- ✅ Google Business Profile verified with physical address; company registration number matches state database

**TD18: Refund Policy (if applicable)** | Stage: Both
- **Pass**: Clear refund policy with timeframes (e.g., 30 days), process description, and exceptions; linked from footer
- **Partial**: Refund policy exists but vague on timeframes or process
- **Fail**: No refund policy mentioned for products/services that typically offer refunds
- N/A if no products/services sold or all sales final
- ❌ E-commerce site selling $200+ items with no mention of refunds anywhere
- ✅ "Refunds within 30 days of delivery. Contact support@example.com with order number. Customer pays return shipping unless item defective."

**TD19: Shipping/Service Terms (if applicable)** | Stage: Both
- **Pass**: Clear shipping terms with delivery timeframes, costs, and geographic restrictions; or clear service-level agreements
- **Partial**: Shipping/service information scattered or incomplete
- **Fail**: No mention of shipping timeframes, costs, or service obligations before purchase
- N/A for digital-only products or content-only sites
- ❌ Checkout page with no indication of shipping cost or delivery time until after payment
- ✅ "Shipping: Free 5-7 day shipping (continental US); Express 2-3 day: $12.99; International: calculated at checkout"

**TD20: GDPR Compliance Depth** | Stage: Both
- **Pass**: Privacy policy specifies: data retention periods, legal basis for processing, DPO contact if required, data categories
- **Partial**: GDPR consent present but policy lacks depth on retention or legal basis
- **Fail**: GDPR-compliant consent banner but privacy policy doesn't specify GDPR-required details
- N/A if site doesn't serve EU users
- ❌ Cookie consent present but privacy policy doesn't specify how long data is kept or legal basis for processing
- ✅ Policy states: "We store analytics data for 26 months (legal basis: legitimate interest); contact form data until request deletion (legal basis: consent)"

---

## SI — Search Integrity

**SI01: No Cloaking** | Stage: Both
- **Pass**: Googlebot and human browser receive the same HTML content and HTTP status codes
- **Partial**: Minor differences (A/B test variants, login state) but not deceptive
- **Fail**: Server detects Googlebot user-agent and returns entirely different content (or a different page)
- ❌ Serving a clean article to Googlebot while showing redirect + ads to users
- ✅ Same HTML returned regardless of User-Agent; JavaScript rendering consistent

**SI02: No Doorway Pages** | Stage: Both
- **Pass**: Every page provides standalone value and is part of a coherent site structure
- **Partial**: Some thin gateway pages that redirect users onward but have some informational content
- **Fail**: Pages exist solely to capture a search query and immediately redirect to a money page
- ❌ 200 city-variation pages ("dentist in Austin", "dentist in Dallas") all redirecting to the same homepage
- ✅ Each location page has genuine local content: hours, address, reviews, local FAQs

**SI03: No Keyword Stuffing** | Stage: Both
- **Pass**: Keywords appear naturally; content reads fluently; no repetitive, unnatural phrasing
- **Partial**: Some repetitive phrasing but still readable and useful
- **Fail**: Keyword blocks, lists of synonyms, or sentences that make no grammatical sense due to keyword insertion
- ❌ "Best cheap flights cheap flight deals cheap flight booking cheap flights online cheap"
- ✅ "Find cheap flights on our flight search engine — compare deals across 500+ airlines."

**SI04: No Hidden Text or Links** | Stage: Both
- **Pass**: All text and links visible to users are also visible in the browser; no CSS/JS tricks hiding content from users but showing to crawlers
- **Partial**: Some content hidden for UX (accordions, tabs) — acceptable if accessible to all users
- **Fail**: White text on white background; text positioned off-screen with `left: -9999px`; zero-opacity links

**SI05: No Deceptive Redirects** | Stage: Both
- **Pass**: All redirects go to pages topically related to the source; no user/bot differentiation in redirect chains
- **Partial**: A few legacy URL redirects that chain through multiple hops but end at the correct destination
- **Fail**: Desktop users see content; mobile users are redirected to unrelated spam sites; or bait-and-switch redirect after click

**SI06: No Scaled Content Abuse** | Stage: Both
- **Pass**: Content is individually crafted or AI-assisted with clear editorial oversight; no mass-publish automation
- **Partial**: Some templated content but each page has meaningful unique data filling the template
- **Fail**: 10,000 auto-generated pages with no meaningful variation; content clearly machine-produced without review
- ❌ Publishing 1,000 AI articles per day with no editing, all targeting "[keyword] + [city]" patterns
- ✅ Using AI to draft, then a human editor refines, adds data, and personalizes each article before publish

**SI07: No Content Scraping** | Stage: Both
- **Pass**: All content is original or licensed; external sources quoted briefly with attribution and added commentary
- **Partial**: Some content summarizes news or aggregates data, but adds analysis or original perspective
- **Fail**: Body text is lifted verbatim from news sites, Wikipedia, or competitor articles

**SI08: Affiliate Content Has Added Value** | Stage: Both
- **Pass**: Affiliate/review pages contain original tests, ratings, user data, or hands-on comparisons
- **Partial**: Affiliate pages include some original commentary but rely heavily on product specs from the merchant
- **Fail**: Affiliate pages are purely reprinted merchant product descriptions with affiliate links appended
- ❌ "The XYZ Blender has 5 speeds, 1000W motor, BPA-free container." [affiliate link] — entirely from Amazon listing
- ✅ "After 3 months of use, the XYZ Blender's seal failed. Here's why I still recommend it for light use and the alternatives I'd try first." [affiliate link]

**SI09: No User-Generated Spam** | Stage: Active
- **Pass**: Comment sections and forums are moderated; spam links removed promptly; nofollow on UGC links
- **Partial**: UGC exists; some spam present but site is being moderated
- **Fail**: Comment sections full of spam links; no moderation; UGC exploited for link injection
- N/A if site has no UGC features

**SI10: No Misleading Functionality** | Stage: Both
- **Pass**: Every tool or feature advertised actually works as described
- **Partial**: Tool has limitations not prominently disclosed (e.g., "free" tool with hidden limits)
- **Fail**: Site advertises functionality it cannot deliver; users are bait-and-switched to advertising or other content
- ❌ "Free iPhone Generator — Enter your address to claim!" (no such generator exists; page collects emails and shows ads)
- ✅ PDF merger tool that actually merges PDFs; free tier clearly labeled with upload size limits

**SI11: Internal Link Anchor Quality** | Stage: Both
- **Pass**: Internal links use descriptive, contextual anchor text that indicates destination content
- **Partial**: Some generic anchors ("click here", "read more") but mostly descriptive
- **Fail**: Internal links use vague/generic anchors; or anchors are keyword-stuffed phrases
- ❌ "For more information, click here to read our post about this topic."
- ✅ "Learn more in our complete guide to on-page SEO optimization."

**SI12: No Orphan Pages** | Stage: Both
- **Pass**: All important content pages have at least one internal link from another page on the site
- **Partial**: A few older posts have no internal links but are accessible via sitemap/category pages
- **Fail**: Many content pages have zero internal links pointing to them; discoverable only via direct URL or search
- ❌ Site has 100 articles but 40 of them have no internal links from other pages
- ✅ Every article has at least 2-3 internal links from related content, homepage, or category pages

**SI13: External Link Quality** | Stage: Both
- **Pass**: External links point to authoritative, trustworthy sources (.edu, .gov, major publishers, industry leaders); no spam sites
- **Partial**: Most links to good sources; occasional link to medium-quality blogs or content farms
- **Fail**: Links to spam sites, PBNs, link schemes, or low-quality article directories
- ❌ Reference links pointing to link farms, paid guest post networks, or sites with spammy appearance
- ✅ Links to: academic papers, government sources, established industry publications, recognized experts

**SI14: Nofollow Correct Usage** | Stage: Both
- **Pass**: Paid links, affiliate links, and UGC (comments, forums) use rel="nofollow", "sponsored", or "ugc" appropriately
- **Partial**: Most risky links use nofollow but some missed; or overuse of nofollow on natural editorial links
- **Fail**: Paid/affiliate links without nofollow; or suspicious link patterns suggesting link schemes
- ❌ Paid review links, sponsored content links, and affiliate links all passing PageRank
- ✅ Sponsored content: `<a rel="sponsored" href="...">`; affiliate links: `<a rel="nofollow" href="...">`; comments: `rel="ugc"`

**SI15: Redirect Chain Length** | Stage: Both
- **Pass**: No redirect chains longer than 3 hops; all redirects use 301 (permanent) status where appropriate
- **Partial**: Most redirects direct; occasional 2-3 hop chains or temporary (302) redirects where 301 would be better
- **Fail**: Redirect chains of 4+ hops; or redirect loops; or excessive use of 302/307 temporary redirects
- ❌ User clicks link → 302 → 301 → 302 → destination (4 hops, mixed redirect types)
- ✅ User clicks link → 301 → destination (clean redirect chain)

**SI16: URL Structure Quality** | Stage: Both
- **Pass**: URLs are descriptive, use hyphens (not underscores), under 100 characters, and avoid unnecessary parameters
- **Partial**: URLs are readable but some are overly long or use inconsistent patterns
- **Fail**: URLs with underscores, excessive parameters, session IDs, or completely non-descriptive slugs
- ❌ `example.com/p=1234?sid=abc987&cat=5` (meaningless parameters)
- ✅ `example.com/blog/seo-guide-for-beginners-2026` (descriptive, hyphens, reasonable length)

---

# Part 6: Output Report Template

```markdown
# AdSense Readiness Report — [Domain]
**Date:** [YYYY-MM-DD]
**Site Type:** [Blog / Tool / Affiliate / News / E-commerce / Forum]
**ARB Version:** 3.0

---

## Overall Result

| Score | Grade | Status |
|-------|-------|--------|
| [X]/100 | [Grade] | [Ready / Minor Fixes / Significant Work / Major Overhaul / Not Ready] |

## Veto Alerts 🚨

[List any triggered veto items here, or "None"]

---

## Pillar Scorecard

| Pillar | Score | Grade | Weight | Weighted |
|--------|-------|-------|--------|---------|
| CI Content Integrity | /100 | | % | |
| PC Policy Compliance | /100 | | % | |
| TH Technical Health | /100 | | % | |
| UX User Experience | /100 | | % | |
| TD Trust & Disclosure | /100 | | % | |
| SI Search Integrity | /100 | | % | |
| **Total** | | | 100% | **/100** |

---

## TOP 5 Priority Fixes

| Priority | Item | Issue | Recommended Action |
|----------|------|-------|--------------------|
| 1 | [ID] | [What failed] | [How to fix it] |
| 2 | | | |
| 3 | | | |
| 4 | | | |
| 5 | | | |

---

## Full Item Results

### CI — Content Integrity
| ID | Item | Status | Score | Notes |
|----|------|--------|-------|-------|
| CI01 | Minimum Content Volume | ✅ Pass / ⚠️ Partial / ❌ Fail | 10/5/0 | |
...

[Repeat table for each pillar]

---
