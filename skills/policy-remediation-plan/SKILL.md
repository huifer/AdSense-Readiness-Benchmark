---
name: policy-remediation-plan
description: "Detailed action plan to fix Policy Compliance violations. Includes content removal procedures, affiliate disclosure templates, privacy policy guidance, and GDPR/CCPA compliance steps."
---

# Policy Remediation Plan

Step-by-step guide to fix policy violations and achieve compliance. Includes templates, legal references, and procedures for each violation type.

## Scope Context

Downstream remediation skill fed by `policy-risk-scanner`.

| Field | Value |
|---|---|
| **Phase** | Remediation |
| **Upstream** | `policy-risk-scanner` |
| **ARB items addressed** | PC01–PC11 (core); PC12–PC13 when flagged as extension |
| **Score mode** | Inherited from `policy-risk-scanner` output — this skill does not independently score |
| **Veto priority** | PC10 (affiliate disclosure) and any PC fail are veto items — fix these first |

Fixes must be re-verified by running `policy-risk-scanner` again under the **same score mode**.

## Purpose

Fix policy compliance violations from `policy-risk-scanner`:
- Remove/revise prohibited content
- Add proper affiliate disclosures
- Implement privacy protections
- Handle regulated content correctly
- Achieve legal compliance (GDPR, CCPA, etc.)

## Critical Violations (Fix Immediately)

### Illegal Content (PC01) — CRITICAL

**Action**:
1. Identify all illegal content pages
2. Immediately remove or make inaccessible (HTTP 410 Gone)
3. Don't just hide with robots.txt (still harmful)
4. Remove from Google Search Console coverage

**Process**:
- Use Google Search Console → Removals → Temporarily hide
- Then permanently delete content after 6 months
- Or HTTP 410 status code

**Example**:
```bash
# Mark as gone
curl -X DELETE https://example.com/illegal-page
# Server returns 410 Gone status code
```

---

### Health Misinformation (PC05) — CRITICAL

**Identify problematic claims**:
- Anti-vaccine content
- COVID-19 denial
- "Miracle cures"
- Dangerous medical advice

**Fix Options**:

**Option 1: Remove**
- Delete page entirely (best)
- Return 410 Gone status code

**Option 2: Substantially Revise**
- Add medical disclaimers
- Cite peer-reviewed studies
- Recommend consulting doctors
- Remove absolute health claims

**Example Before/After**:
```
BEFORE: "This supplement cures diabetes"
AFTER: "This supplement may support blood sugar levels.
        Always consult your doctor. See study: [link]"
```

**Add Disclaimers**:
```html
<div class="medical-disclaimer">
  <strong>Medical Disclaimer:</strong> This information is
  not medical advice. Always consult a healthcare provider.
</div>
```

---

### Malware Distribution (PC07) — CRITICAL

**Action**:
1. Identify malicious downloads
2. Remove immediately (410 Gone)
3. Scan server for compromise
4. Update passwords and security
5. Use hashed upload verification

**Prevention**:
```html
<!-- Clear consent before download -->
<p>By clicking download, you accept our terms.</p>
<a href="safe-file.zip" class="btn-download">Download</a>

<!-- Verify file hash -->
SHA256: a3f8e2b9c1d6f4e7a9b0c1d2e3f4a5b6c7d8e9f0a1b2c3d4e5f6a7b8c9d0e1
```

---

### Deceptive Claims (PC04)

**Examples**:
- "Guaranteed weight loss"
- "Make $1000/day"
- "Cure arthritis"

**Fix**:
```
BEFORE: "Guaranteed to work"
AFTER: "May help. Results vary. [Study: 60% users saw improvement]"

BEFORE: "$10,000/month guaranteed"
AFTER: "Average earnings: $500-2000/month. Depends on effort."

BEFORE: "Cure arthritis"
AFTER: "Support joint health. [3rd-party tested]"
```

Add:
- Disclaimers
- Realistic expectations
- Scientific references
- "Results may vary"

---

## High-Priority Fixes

### Affiliate Disclosure (PC10) — HIGH

**Required**: Visible disclosure on any affiliate content

**Simple Fix**: Add 1 sentence near the top/link

**Template**:
```
"As an Amazon Associate, we earn from qualifying purchases."
"We may earn a commission if you purchase through our links."
"Affiliate disclosure: We earn from purchases you make
through our referral links."
```

**Placement**:
- Option 1: Above content (best visibility)
- Option 2: Inline with first affiliate link (acceptable)
- Option 3: Bold in footer (minimum requirement)

**Code Example**:
```html
<div class="affiliate-disclosure">
  <strong>Affiliate Disclosure:</strong> This page contains
  affiliate links. We may earn a commission if you purchase.
</div>

<!-- Content with links -->
<p>We recommend: <a href="amazon-link">Product</a></p>
```

**Compliance**:
- FTC requirement (USA)
- ASA requirement (UK)
- DGCCRF requirement (France)
- Similar requirements in EU, Canada, Australia

---

### Privacy Policy Update (PC11)

**Minimum Required Information**:

```markdown
# Privacy Policy

## 1. Data Collection
- What data we collect (emails, browsing behavior, etc.)
- How we collect it (forms, cookies, analytics)
- Why we collect it (email marketing, analytics, etc.)

## 2. Data Usage
- How we use the data
- Who we share it with (analytics providers, advertisers, etc.)
- Retention period (how long we keep it)

## 3. User Rights
- Right to access their data
- Right to delete their data
- Right to opt-out of marketing
- How to submit data requests

## 4. GDPR Compliance (if applicable)
- Legal basis for processing
- Data Protection Officer contact
- EU data rights

## 5. CCPA Compliance (if California users)
- California resident rights
- Do Not Sell My Personal Information link
- How to submit requests
```

**Implementation**:
1. Use template generator (Termly, Iubenda, etc.)
2. Add data deletion form
3. Add unsubscribe mechanism
4. Make privacy policy easily accessible
5. Update cookie consent banners

**Example Data Deletion Form**:
```html
<form method="POST" action="/delete-data">
  <input type="email" placeholder="Your email" required>
  <textarea placeholder="Which data to delete?"></textarea>
  <button type="submit">Request Deletion</button>
  <!-- Response within 30 days (GDPR requirement) -->
</form>
```

---

### Regulated Content (PC09)

**For Gambling Content**:
- Get explicit gambling license/certification
- Use separate AdSense gambling account
- Geofence content (illegal in many regions)
- Age gate (18+ verification)

**For Tobacco Content**:
- Limited to education/advocacy only
- No promotion or sales
- Age restriction recommended
- Disclaimer required

**For Alcohol Content**:
- Advocacy/education allowed
- No direct sales through ads
- Age restriction (18-21 depending on country)
- Responsible drinking messaging

---

## Medium Priority Fixes

### Ad Code Placement (PC13)

**Correct Placement**:
```html
<head>
  <!-- Option 1: In head (Google recommends) -->
  <script async src="https://pagead2.googlesyndication.com/..."></script>
</head>
<body>
  <!-- or -->
  
  <!-- Option 2: Before closing body -->
  <script async src="https://pagead2.googlesyndication.com/..."></script>
</body>
```

**Incorrect** (These cause issues):
```html
<!-- Don't put in comments -->
<!-- <script async src="..."></script> -->

<!-- Don't break the script -->
<script> (broken code) </script async src="...">

<!-- Don't use wrong type -->
<script type="text/html" src="..."></script>
```

---

### Regulated Content Handling (PC09)

**Gambling**: Requires special agreement + geofencing
**Tobacco**: Educational content only, no sales
**Alcohol**: Advocacy + age restrictions

---

## Action Plan Template

```markdown
# Policy Remediation Action Plan

## Critical Issues (Week 1)
- [ ] Remove anti-vaccine content (3 pages)
  - Pages: /health/vaccines, /blog/alternative-medicine
  - Action: 410 Gone status code
  - Timeline: Today
  - Verification: Google Search Console removal request

- [ ] Remove illegal content (1 page)
  - Pages: /downloads/hacking-guide
  - Action: Complete deletion
  - Timeline: Today
  - Verification: Server 404 response

## High Priority Issues (Week 1-2)
- [ ] Add affiliate disclosures (45 posts)
  - Template: "As an Amazon Associate..."
  - Timeline: 4 hours
  - Verification: Manual spot-check

- [ ] Update privacy policy
  - Add data deletion process
  - Add GDPR clauses (if EU visitors)
  - Timeline: 2-3 hours
  - Verification: Privacy policy review

## Medium Priority Issues (Week 2-3)
- [ ] Fix ad code placement
  - Move from footer to head
  - Timeline: 30 min
  - Verification: Code audit

- [ ] Add gambling disclaimer (if applicable)
  - Timeline: 1 hour
```

---

## Templates & Documents

### Affiliate Disclosure Template
```
"As an Amazon Associate, [Your Company] earns from qualifying purchases."
```

### Privacy Policy Checklist
- [ ] Data collection explained
- [ ] Data usage explained
- [ ] User rights section
- [ ] Contact information
- [ ] GDPR/CCPA sections (if applicable)
- [ ] Cookie consent
- [ ] Data deletion process

### GDPR Compliance (EU Users)
- [ ] Privacy policy updated with GDPR terms
- [ ] Lawful basis for processing specified
- [ ] Data Protection Officer contact (if needed)
- [ ] Data deletion capability
- [ ] Consent management system

### CCPA Compliance (California Users)
- [ ] Privacy policy with California rights
- [ ] "Do Not Sell My Personal Information" link
- [ ] Data access request capability
- [ ] Deletion request capability

---

## Success Metrics

- [ ] No illegal content remaining (verify via crawl)
- [ ] All affiliate content has visible disclosure
- [ ] Privacy policy complete and accessible
- [ ] Data deletion process working
- [ ] Ad code properly placed
- [ ] Regulated content properly handled/removed
- [ ] No policy-related rejections

---

## Verification Checklist

1. **Content Check**:
   ```bash
   # Search for prohibited keywords
   grep -r "anti-vaccine\|miracle cure\|get rich" content/
   ```

2. **Affiliate Check**:
   - Manual spot-check 10 affiliate pages
   - Verify disclosure visible and clear

3. **Policy Check**:
   - Privacy policy accessible from all pages
   - Policy is current (updated within 1 year)
   - Data deletion process working

4. **Code Check**:
   - Verify ad code in correct location
   - Run HTML validation
   - Check console for errors

---

**Related Skills**:
- Scan results → `policy-risk-scanner`
- Verify fixes → `resubmission-readiness-check`
