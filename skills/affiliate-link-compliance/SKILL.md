---
name: affiliate-link-compliance
description: "Verify all affiliate link disclosures for FTC, ASA, and international compliance. Finds undisclosed affiliate links and ensures proper format."
---

# Affiliate Link Compliance

Comprehensive verification of affiliate link disclosures across your entire site. Ensures FTC, ASA, and international compliance.

## Scoring Mode & Aggregation Contract

| Field | Value |
|---|---|
| **Scope** | Cross-phase check — always runs when site has any affiliate content, regardless of score mode |
| **Core 79 items covered** | PC10 (affiliate disclosure — veto item), TD08 (privacy policy affiliate mention) |
| **Extension items covered** | PC12–PC13 coverage when gambling/regulated affiliate programs present |
| **Veto items** | PC10 — any disclosure failure = instant pillar veto; escalate immediately |
| **Mode interaction** | This skill contributes to `PC` and `TD` pillars; report findings under both |

**Output fields required** (for aggregation by `ads-readiness-assessment`):
- `score_mode`: inherit from calling orchestrator
- `pillars_affected`: `["PC", "TD"]`
- `items_evaluated`: e.g., `["PC10", "TD08"]`
- `veto_triggered`: `true` / `false` + which item(s)
- `undisclosed_links_found`: count + URLs
- `disclosure_format_issues`: list of non-compliant disclosure formats

**Rule**: If site has no affiliate links, output `affiliate_scope: none` and skip all checks — do not mark items as `not_in_scope` (they simply do not apply).

## Purpose

Audit affiliate link compliance:
- Identify all affiliate links
- Verify proper disclosure
- Ensure visibility and clarity
- Comply with all regulations
- Prevent policy violations

## Quick Start

**Input**: Website URL or source files
**Output**: Affiliate link inventory + compliance report
**Time**: 15-30 minutes

## Compliance Standards

### FTC (USA)
**Requirement**: Clear and conspicuous disclosure
**Placement**: Before the link or at beginning of content
**Language**: "Affiliate disclosure", "We earn commissions", "As an Amazon Associate"
**Penalty**: False advertising violation + legal action

### ASA (UK)
**Requirement**: Clear identification of commercial relationship
**Format**: #ad or #sponsored on social media, disclaimer on content
**Placement**: Prominent location
**Penalty**: Fine, removal from advertising

### EU (GDPR & Ecommerce)
**Requirement**: Transparent affiliate relationship
**Disclosure**: Required in privacy policy
**Format**: Clear and honest language
**Penalty**: Fine up to €20,000

### Canada (MACT)
**Requirement**: Clear disclosure of material connection
**Format**: "We may earn commission"
**Placement**: Before user decision
**Penalty**: Fine + damages

---

## Affiliate Link Audit Process

### Step 1: Inventory All Affiliate Links

**Identify affiliate URL patterns**:
- Amazon: amazon.com/?tag=yourtag
- CJA: cjdropshipping.com/?ref=
- Impact: /click/
- Rakuten: rakuten.com?_l=en
- ... (others)

**Automated script**:
```bash
# Find affiliate patterns in HTML
grep -r "amazon.com/.*tag=" ./website/
grep -r "cjdropshipping.com/.*ref=" ./website/
grep -r "/?affiliate=" ./website/
```

### Step 2: Check Disclosure Presence

For each page with affiliate links:
- [ ] Is there ANY disclosure statement?
- [ ] Is it before the links? (best)
- [ ] Is it after the links? (acceptable)
- [ ] Is it in fine print? (risky)
- [ ] Is it in footer only? (borderline)

**Good Disclosure Locations**:
1. ✅ Before the first affiliate link (best)
2. ✅ In a "Disclosure" section at top of post
3. ✅ Immediately next to the link
4. ⚠️ In a separate "Affiliate Links" section on page
5. ❌ In footer only (often missed by users)
6. ❌ In privacy policy only (not visible where it matters)

### Step 3: Evaluate Disclosure Quality

**Clear & Conspicuous Test**:
- [ ] Can users easily see it?
- [ ] Is it in natural language (not legalese)?
- [ ] Does it clearly explain the relationship?
- [ ] Is it hard to miss?

**Examples**:

✅ **Good Disclosure**:
```
"As an Amazon Associate, we earn from qualifying purchases.
This does not affect the price you pay."
```

✅ **Good Disclosure**:
```
"Affiliate Disclosure: This post contains Amazon affiliate
links. If you purchase through these links, we receive a
small commission at no extra cost to you."
```

❌ **Poor Disclosure** (too hidden):
```
"*See disclosure policy in footer for affiliate
relationship details."
[User never sees footer]
```

❌ **Poor Disclosure** (unclear):
```
"Some of our content may contain commercial relationships."
[Vague, doesn't say what kind]
```

### Step 4: Generate Compliance Report

```markdown
# Affiliate Link Compliance Report

## Summary
- Total pages reviewed: 150
- Pages with affiliate links: 45
- Compliant disclosures: 40
- Non-compliant or missing: 5
- Compliance Rate: 89%

## Non-Compliant Pages (Action Required)

### Critical (Missing Disclosure)
- /blog/top-products
- /reviews/gadgets
- /comparison/tools

Action: Add disclosure statement immediately

### Medium (Disclosure Hidden)
- /guides/best-practices
- /tutorials/setup

Action: Move disclosure to more prominent location

## Recommendations
1. Add disclosure to [X] pages
2. Move [Y] disclosures to more visible location
3. Clarify [Z] disclosure statements
```

---

## Disclosure Templates by Platform

### Standard Affiliate Disclosure
```html
<div class="affiliate-disclosure">
  <strong>Affiliate Disclosure:</strong> This post contains
  affiliate links. If you purchase through our links, we may
  earn a small commission at no extra cost to you.
</div>
```

### Amazon Associates
```html
<p><strong>As an Amazon Associate, we earn from qualifying
purchases.</strong> This does not affect the price you pay.</p>
```

### Multiple Affiliate Networks
```html
<p><strong>Disclosure:</strong> This post contains affiliate
links from Amazon Associates, CJ Affiliate, and Shareasale.
We earn a commission if you purchase through these links.</p>
```

### Per-Link Disclosure
```html
<p>Check price on <a href="amazon-link">Amazon*</a></p>
<p>*Affiliate link: We earn a commission</p>
```

### CSS-Based Visible Disclosure
```css
.affiliate-link::after {
  content: " [affiliate link]";
  color: #999;
  font-size: 0.9em;
}
```

---

## Compliance Checklist

- [ ] All affiliate links identified
- [ ] Disclosure on every page with affiliate links
- [ ] Disclosure BEFORE the affiliate link
- [ ] Disclosure clear and in plain language
- [ ] No misleading about commission/cost
- [ ] Privacy policy mentions affiliate relationships
- [ ] FTC/ASA standards met
- [ ] Tested for visibility
- [ ] Mobile version also compliant

---

## Common Non-Compliance Issues

**Issue 1: No Disclosure**
- Page has affiliate links but no disclosure
- Fix: Add disclosure immediately (FTC violation)

**Issue 2: Hidden Disclosure**
- Disclosure in footer, not visible above fold
- Fix: Move to top of post or near links

**Issue 3: Vague Disclosure**
- "Commercial relationship" but doesn't say what
- Fix: "Affiliate links - we earn commissions"

**Issue 4: Disclosure Only in Footer/Policy**
- Users don't see it where it matters
- Fix: Add to each post with affiliate links

**Issue 5: Misleading Statement**
- "This doesn't affect your price" when it does
- Fix: Be honest about commission structure

---

## Geographic Compliance

**USA (FTC)**:
- Clear disclosure required
- "Affiliate" or "We earn commissions"
- Before link preferred

**UK (ASA)**:
- #ad or #sponsored on social
- Clear on webpage
- "Affiliate" label

**EU (GDPR)**:
- Transparent about relationships
- Privacy policy must mention
- Must be fair and honest

**Canada (MACT)**:
- Clear "material connection" disclosure
- Before user makes decision
- Honest representation

---

## Automation Script

**Find non-compliant pages**:
```javascript
const fs = require('fs');
const path = require('path');

function checkAffiliateLinkCompliance(htmlContent) {
  const affiliateRegex = /amazon\.com\/.*\?tag=|cjdropshipping\.com\/.*\?ref=|click\.../g;
  const disclosureRegex = /affiliate|commission|earn|compensat/i;

  const hasAffiliateLinks = affiliateRegex.test(htmlContent);
  const hasDisclosure = disclosureRegex.test(htmlContent);

  if (hasAffiliateLinks && !hasDisclosure) {
    return { compliant: false, reason: 'Missing disclosure' };
  }

  if (hasAffiliateLinks && hasDisclosure) {
    const disclosureIndex = htmlContent.indexOf(disclosureRegex);
    const affiliateIndex = htmlContent.indexOf(affiliateRegex);
    if (disclosureIndex > affiliateIndex) {
      return { compliant: false, reason: 'Disclosure after links' };
    }
  }

  return { compliant: true };
}
```

---

## Success Metrics

- [ ] 100% of affiliate link pages have disclosure
- [ ] 100% of disclosures before links
- [ ] All disclosures clear and conspicuous
- [ ] No FTC violations or complaints
- [ ] Compliant with all geographic requirements

---

**Related Skills**:
- Policy compliance → `policy-risk-scanner`, `policy-remediation-plan`
- Full audit → `ads-readiness-assessment`
- Active monitoring → `active-compliance-monitor`
