---
name: rejection-root-cause-analysis
description: "Analyze Google rejection notices to identify root causes. Maps Google's feedback to specific ARB criteria and provides prioritized remediation paths."
---

# Rejection Root Cause Analysis

Analyze your Google AdSense rejection notice to understand exactly why you were rejected and what needs to be fixed.

## Scope Context

Entry point for the rejection recovery path. Maps Google's feedback to specific ARB item IDs and declares the scope for downstream audits.

| Field | Value |
|---|---|
| **Phase** | Post-rejection analysis |
| **Downstream** | `recovery-action-plan`, `appeal-strategy-builder` |
| **ARB item coverage** | All pillars (CI, PC, TH, UX, TD, SI) — scope depends on rejection type |
| **Score mode declared** | `Core 79 + Profile` for targeted re-audit; `Full 105` when Google cites broad quality issues |

Output **must** include:
- `recommended_score_mode`: the scope to use for follow-up audits
- `primary_site_type`: to select the correct extension profile
- `mapped_items`: list of ARB item IDs matched to each rejection reason

## Purpose

Transform rejection notice into actionable insights:
- Map Google's feedback to specific ARB criteria
- Identify root causes vs. symptoms
- Prioritize fixes
- Create targeted remediation plan
- Prevent re-rejection

## Quick Start

**Input**: Google rejection notice (text or screenshot)
**Output**: Root cause analysis + ARB mapping + remediation priorities
**Time**: 15-30 minutes

## Workflow

### Step 1: Extract Rejection Reason

Review Google's email for key phrases:
- "Policy violation"
- "Low-value content"
- "Spam practices"
- "Deceptive design"
- "Technical issues"

### Step 2: Map to ARB Criteria

**Google says... → ARB Criteria:**

| Google's Feedback | Likely Criteria | Common Root Cause |
|---|---|---|
| "Low-value content" | CI01-CI03 | Thin pages, lack of depth, copied content |
| "Poor user experience" | UX02-UX06 | Intrusive ads, deceptive design, poor layout |
| "Deceptive practices" | PC04, PC06 | Misleading claims, false health claims |
| "Multiple policy violations" | PC01-PC08 | Prohibited content present |
| "Technical issues" | TH01-TH05 | HTTPS missing, broken links, sitemap issues |
| "Insufficient contact information" | TD | Missing about/contact page |
| "Health/financial claims" | PC04-PC05 | Misinformation, unverified claims |

### Step 3: Categorize Issues

**By Severity**:
- Critical: Blocks all reapplications until fixed
- High: Likely re-rejection if not fixed
- Medium: May cause re-rejection
- Low: Minor issue, unlikely to affect decision

**By Effort**:
- Quick: <1 hour to fix
- Medium: 1-8 hours
- Complex: 1-5 days
- Extensive: 1+ weeks

### Step 4: Create Action Plan

Address critical + quick fixes first

### Step 5: Document Changes

Track what was fixed for resubmission

---

## Common Rejection Reasons & Root Causes

### "Low-Value Content" (CI)

**Google Feedback**:
"Your site contains pages with insufficient original, high-quality content that provides value to users."

**Root Causes**:
- [ ] Pages <300 words (CI01)
- [ ] Copied content from other sites (CI02)
- [ ] Generic, non-unique content (CI03)
- [ ] Thin pages at scale (CI06)
- [ ] Excessive self-duplication (CI07)

**Fix Strategy** (2-6 weeks):
1. Identify all pages <300 words
2. Expand to 300-1000+ words
3. Add unique perspective
4. Remove duplicates
5. Consolidate similar pages
6. Verify with audit tool

---

### "Poor User Experience" (UX)

**Google Feedback**:
"Your site has issues that negatively impact the user experience, such as intrusive ads or deceptive design."

**Root Causes**:
- [ ] Full-screen pop-ups on load (UX03)
- [ ] Ads covering >30% of viewport (UX02)
- [ ] Fake close buttons (UX06)
- [ ] Not mobile-responsive (UX07, UX14)
- [ ] Poor navigation (UX01)
- [ ] Intrusive ads on top (UX08)

**Fix Strategy** (1-2 weeks):
1. Remove or delay pop-ups
2. Relocate ads below fold
3. Add real close buttons
4. Ensure mobile responsiveness
5. Improve navigation structure
6. Add viewport meta tag

---

### "Health Misinformation" (PC05)

**Google Feedback**:
"Your site contains health-related content that goes against scientific consensus or promotes dangerous practices."

**Root Causes**:
- [ ] Anti-vaccine claims
- [ ] COVID denial/misinformation
- [ ] Unsupported medical claims
- [ ] Dangerous health advice
- [ ] Promotion of unproven treatments

**Fix Strategy** (1-3 weeks):
1. Identify all health claims
2. Fact-check against WHO, CDC, peer-reviewed studies
3. Remove false claims OR add disclaimers
4. Cite scientific studies
5. Recommend consulting doctors
6. Remove absolute language ("cures", "guarantees")

---

### "Deceptive Content" (PC04)

**Google Feedback**:
"Your site contains deceptive or misleading information designed to manipulate users."

**Root Causes**:
- [ ] False financial claims ("Make $10,000/day")
- [ ] Misleading testimonials
- [ ] Fake statistics
- [ ] Exaggerated product claims
- [ ] Misleading comparisons

**Fix Strategy** (3-7 days):
1. Audit all claims for accuracy
2. Remove false claims
3. Add supporting evidence
4. Use conservative language
5. Add disclaimers
6. Cite sources

---

### "No Contact Information" (TD)

**Google Feedback**:
"Your site lacks sufficient contact information or transparency."

**Root Causes**:
- [ ] No about page
- [ ] No contact form
- [ ] No physical address
- [ ] No author information
- [ ] No email listed

**Fix Strategy** (1-2 days):
1. Create about page with:
   - Company background
   - Author credentials
   - Team photos
   - Company mission
2. Add contact page with:
   - Contact form
   - Email address
   - Phone number
   - Physical address
3. Add author bios to content

---

### "Spam Indicators" (SI)

**Google Feedback**:
"Your site shows signs of spam or manipulative practices."

**Root Causes**:
- [ ] Keyword stuffing
- [ ] Hidden text
- [ ] Cloaking (different content for Googlebot)
- [ ] Spammy links
- [ ] Auto-generated content

**Fix Strategy** (1-2 weeks):
1. Audit for keyword stuffing
2. Remove hidden text/links
3. Ensure same content for all users
4. Audit inbound/outbound links
5. Verify all content is original/valuable
6. Remove auto-generated pages

---

### "Technical Issues"

**Google Feedback**:
"Technical problems prevent us from properly reviewing your site."

**Root Causes**:
- [ ] No HTTPS (TH01) — CRITICAL
- [ ] No sitemap (TH04)
- [ ] Broken robots.txt (TH03)
- [ ] Too many 404s (TH08)
- [ ] Page load >3 sec (TH06)

**Fix Strategy** (1-4 hours):
1. Enable HTTPS immediately
2. Create/update XML sitemap
3. Verify robots.txt allows crawling
4. Fix broken links
5. Optimize performance
6. Test with Google Search Console

---

## Rejection Analysis Template

```markdown
# Rejection Analysis Report

## Original Rejection Reason
[Copy Google's exact feedback]

## Root Cause Assessment

### Primary Causes
- [ ] [Issue 1] - [Severity: Critical/High/Medium]
- [ ] [Issue 2] - [Severity: ...]

### Contributing Factors
- [ ] [Issue 3]
- [ ] [Issue 4]

## ARB Criteria Mapping
- Primary: [CI01, CI02, etc.]
- Secondary: [TH01, TH02, etc.]

## Fix Priority

### Week 1 (Critical)
1. [Fix 1] - [1-2 hours]
2. [Fix 2] - [2-4 hours]

### Week 2 (High)
3. [Fix 3] - [4-8 hours]
4. [Fix 4] - [Ongoing]

### Week 3+ (Medium)
5. [Fix 5]

## Estimated Timeline
Total: 2-4 weeks

## Success Criteria
- [ ] All critical issues resolved
- [ ] Re-audit shows improvement
- [ ] No remaining policy violations
```

---

## Common Patterns

### Pattern 1: Multiple Small Issues
**Signs**: "We found several issues..."
**Approach**: Fix each category systematically
**Timeline**: 2-3 weeks

### Pattern 2: Single Major Issue
**Signs**: "Your site contains..."
**Approach**: Focus on that category
**Timeline**: 1-2 weeks

### Pattern 3: Low-Value Content
**Signs**: "Insufficient original content"
**Approach**: Expand thin pages, add unique value
**Timeline**: 3-6 weeks

### Pattern 4: UX/Design Issues
**Signs**: "Poor user experience"
**Approach**: Remove pop-ups, optimize layout
**Timeline**: 1-2 weeks

---

## Next Steps

1. **Complete this analysis** (15-30 min)
2. **Review in** `recovery-action-plan` skill
3. **Execute fixes** using relevant improvement guides
4. **Re-verify** with `resubmission-readiness-check`
5. **Resubmit** when ready

---

**Related Skills**:
- Create action plan → `recovery-action-plan`
- Verify fixes → `resubmission-readiness-check`
- Appeal (if disputing) → `appeal-strategy-builder`
