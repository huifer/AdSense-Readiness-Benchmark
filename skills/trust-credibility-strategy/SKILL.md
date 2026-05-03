---
name: trust-credibility-strategy
description: "Multi-phase strategy to build user trust and site credibility. Includes about page optimization, author verification, security signals, and user review integration."
---

# Trust & Credibility Strategy

Strategic plan to build user trust and site authority. Encompasses about pages, author credentials, security signals, and user engagement elements that signal legitimacy to both users and Google.

## Scope Context

Downstream remediation skill for the Trust & Disclosure (TD) pillar.

| Field | Value |
|---|---|
| **Phase** | Remediation |
| **Upstream** | `ads-readiness-assessment` (TD pillar section) |
| **ARB items addressed** | TD01–TD14 (core); TD15–TD20 when flagged as extension |
| **Score mode** | Inherited from `ads-readiness-assessment` output — this skill does not independently score |
| **Veto priority** | TD01 (Privacy Policy) is a veto item — always the highest priority fix |

Improvements must be re-verified through `ads-readiness-assessment` under the **same score mode**.

## Purpose

Build Trust & Disclosure (TD) pillar strength:
- Author and organizational credibility
- Transparent ownership and contact information
- Security and trust signals
- User reviews and testimonials
- Professional presentation and design

## 4-Week Implementation Plan

### Week 1: About & Contact Foundation

**About Page Enhancement**
- [ ] Write compelling "About Us" page (500-800 words)
- [ ] Include company/author photo/logo
- [ ] Explain mission and values
- [ ] Highlight relevant expertise or experience
- [ ] Link to social profiles (if strong)

**About Page Template**:
```markdown
# About [Company/Author]

## Our Story
[Company background, why we started, mission]

## Our Expertise
[Years in industry, specific expertise areas]

## Our Team
[Photos and bios of key team members]
- Name, role, credentials/experience

## Values We Stand For
- Value 1: [Explanation]
- Value 2: [Explanation]
- Value 3: [Explanation]

## Recognition & Awards
[Industry certifications, awards, media mentions]

## Contact Us
[Contact form or email]
[Physical address if applicable]
```

**Contact Page**
- [ ] Contact form or email prominently visible
- [ ] Response time commitment ("We respond in 24 hours")
- [ ] Multiple contact methods (email, phone, form)
- [ ] Physical address (if applicable)
- [ ] Business hours (if applicable)

---

### Week 2: Author & Credentials

**Add Author Information**
- [ ] E-E-A-T signals (Experience, Expertise, Authority, Trustworthiness):
  - Experience: Years in field, past work
  - Expertise: Certifications, education, specialization
  - Authority: Media mentions, speaking engagements, awards
  - Trustworthiness: Transparency, conflict of interest disclosure

**Author Schema Markup**:
```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "Person",
  "name": "Jane Doe",
  "url": "https://example.com/about/jane-doe",
  "image": "https://example.com/images/jane.jpg",
  "jobTitle": "SEO Expert",
  "affiliation": {
    "@type": "Organization",
    "name": "Example Company"
  },
  "sameAs": ["https://twitter.com/janedoe"],
  "knowsAbout": ["SEO", "Content Marketing", "Technical SEO"]
}
</script>
```

**Author Bio Enhancement** (on content pages):
- [ ] Add author name and photo to articles
- [ ] Link to author profile
- [ ] Include 1-2 sentence credentials
- [ ] Example: "Jane Doe is an SEO expert with 10+ years experience"

---

### Week 3: Security & Trust Signals

**Security Badges**
- [ ] Get SSL certificate (should already have for HTTPS)
- [ ] Display security badge (Norton, McAfee, etc. - optional)
- [ ] Show trust seals if industry-specific (e.g., FDA, FTC)

**Privacy & Security Transparency**
- [ ] Privacy policy (visible in footer)
- [ ] Terms of Service
- [ ] Refund policy (if applicable)
- [ ] No hidden fees or surprise charges

**SSL Certificate Verification**:
```html
<!-- Already in HTTP header; optional visual indicator -->
<div class="trust-badges">
  <img src="ssl-badge.png" alt="SSL Secure">
  <img src="secure-site.png" alt="Verified Secure">
</div>
```

---

### Week 4: User Reviews & Engagement

**Collect Reviews**
- [ ] Google Reviews setup (for businesses)
- [ ] Trustpilot or similar review platform
- [ ] Display reviews on website
- [ ] Respond to both positive and negative reviews

**Schema Markup for Reviews**:
```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "AggregateOffer",
  "ratingValue": "4.8",
  "reviewCount": "240",
  "reviews": [
    {
      "@type": "Review",
      "reviewRating": { "@type": "Rating", "ratingValue": "5" },
      "reviewBody": "Excellent service...",
      "author": { "@type": "Person", "name": "John Smith" }
    }
  ]
}
</script>
```

**Testimonials Section**
- [ ] 5-10 customer testimonials with photos/names
- [ ] Real quotes (not generic)
- [ ] Can include video testimonials (highest trust)

**Social Proof Elements**
- [ ] User count/community size ("50,000+ customers")
- [ ] Years in business ("Trusted since 2015")
- [ ] Media mentions ("Featured in Forbes, TechCrunch")
- [ ] Industry awards/certifications

---

## Advanced Trust Building

### Transparency Measures

**Conflict of Interest Disclosure**
- [ ] Affiliate disclosures (already covered in policy-remediation-plan)
- [ ] Sponsored content clearly marked
- [ ] Financial relationships disclosed
- [ ] Template: "This post contains affiliate links"

**Editorial Standards Page**
- [ ] How content is created
- [ ] Fact-checking process
- [ ] Correction policy
- [ ] Source documentation

**Data & Methodology**
- [ ] Explain data sources for statistics
- [ ] Show methodology for research/tests
- [ ] Cite peer-reviewed studies
- [ ] Link to original sources

### Authority Building

**Content Attribution**
- [ ] All quotes properly attributed
- [ ] Images properly credited
- [ ] Data sources cited
- [ ] Contributors acknowledged

**Expert Contributors**
- [ ] Feature guest posts from recognized experts
- [ ] Include expert quotes with credentials
- [ ] Link to expert bios
- [ ] Cross-promote expert work

**Industry Involvement**
- [ ] Speaking at conferences
- [ ] Contributing to industry publications
- [ ] Participating in professional organizations
- [ ] Share these achievements on website

### Business Legitimacy

**Transparency Information**
- [ ] Business registration visible (if applicable)
- [ ] Address verifiable on Google Maps
- [ ] Phone number working and monitored
- [ ] Business hours listed

**Business Schema Markup**:
```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "LocalBusiness",
  "name": "Example Company",
  "url": "https://example.com",
  "telephone": "+1-555-0100",
  "address": {
    "@type": "PostalAddress",
    "streetAddress": "123 Main St",
    "addressLocality": "Anytown",
    "addressRegion": "CA",
    "postalCode": "90210"
  },
  "image": "https://example.com/logo.png"
}
</script>
```

---

## Trust Building Checklist

- [ ] About page >500 words with team info
- [ ] Author credentials visible on all major content
- [ ] Contact information easy to find
- [ ] Privacy policy and Terms of Service present
- [ ] No misleading claims or design
- [ ] Affiliate disclosures clear
- [ ] Reviews/testimonials with real names/photos
- [ ] SSL certificate valid and working
- [ ] Social profiles linked (if strong)
- [ ] Physical address verifiable
- [ ] Response to emails/inquiries within 24 hours

---

## Content Quality = Trust

**E-E-A-T for Content**:

1. **Experience**
   - Personal experience with topic
   - Case studies or examples
   - Lessons learned
   - Outcome/results

2. **Expertise**
   - Credentials mentioned
   - Years in industry
   - Specific knowledge demonstrated
   - Accurate information

3. **Authority**
   - Cited by other authorities
   - Link profile
   - Industry recognition
   - Media mentions

4. **Trustworthiness**
   - No exaggeration
   - Clear disclaimers where needed
   - Honest about limitations
   - No misleading claims

---

## Trust Metrics to Monitor

Track using Google Analytics or similar:

- [ ] Time on page (higher = more engaged)
- [ ] Bounce rate (lower = more compelling)
- [ ] Return visitor rate (higher = trusted)
- [ ] Click-through rate from search (higher = trusted in SERP)
- [ ] Share rate (higher = seen as authoritative)
- [ ] Customer/user retention (highest trust indicator)

---

## Common Trust Mistakes to Avoid

- ❌ Fake testimonials (use real ones)
- ❌ Stock photos for team bios (use real photos)
- ❌ Exaggerated claims (be conservative)
- ❌ No contact information (include it)
- ❌ Outdated content (keep fresh)
- ❌ No author information (add credentials)
- ❌ Broken links (maintain site health)
- ❌ Slow website (speed = trust)
- ❌ Poor mobile experience (mobile = trust)
- ❌ Excessive ads (cluttered = untrustworthy)

---

## Success Metrics (6-8 weeks)

- [ ] E-E-A-T signals strengthened across site
- [ ] Author credentials visible on key pages
- [ ] Trust badges/certifications displayed
- [ ] Reviews/testimonials on homepage
- [ ] No trust-related rejection reasons
- [ ] Improved click-through rate from search results
- [ ] Increased time-on-page metrics

---

**Related Skills**:
- Full site assessment → `ads-readiness-assessment`
- Verify fixes → `resubmission-readiness-check`
