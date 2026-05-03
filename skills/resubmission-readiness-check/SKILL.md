---
name: resubmission-readiness-check
description: "Final pre-submission verification. Comprehensive checklist ensuring all fixes are complete and site passes all ARB criteria before resubmitting to Google."
---

# Resubmission Readiness Check

Final verification before resubmitting to Google. Ensures all fixes are complete and site passes all evaluation criteria.

## Purpose

Validate that your site is ready:
- All critical issues fixed
- All audits passing
- No recurrence of original rejection reasons
- Confident chance of approval

## Quick Start

**Input**: Completed recovery actions
**Output**: Final approval/flag report + resubmission checklist
**Time**: 1-2 hours for full verification

## Scoring Mode & Aggregation Contract

This skill is the final verifier. It should never summarize readiness without naming the scope used.

- Acceptable score modes: `Core 79`, `Core 79 + Profile`, `Full 105`
- Recommended mode for actual resubmission decisions: `Core 79 + Profile` at minimum
- Recommended mode for public-facing or mixed-model sites: `Full 105`

Final reports should include:
- `score_mode`
- `primary_site_type`
- `selected_profile_items`
- `triggered_extension_items`
- `veto_summary`
- `ready_for_resubmission` with explanation tied to the chosen scope

## Pre-Resubmission Verification

### Phase 1: Quick Health Check (15 min)

Run automated audit:
```bash
npm run ads-readiness-assessment --site-url https://example.com
```

Review scores:
- [ ] Overall score ≥70/100
- [ ] Score mode declared in the report
- [ ] No Critical issues
- [ ] <5 High priority issues (and documented as acceptable)

### Phase 2: Original Issue Re-Audit (30 min)

For each rejection reason, verify fix:

**If rejected for "Low-Value Content"**:
- [ ] Run content-audit again
- [ ] Verify all pages ≥300 words
- [ ] Confirm <10% thin pages
- [ ] Check originality scores improved
- [ ] Spot-check 5 pages manually

**If rejected for "Poor UX"**:
- [ ] Run ux-compliance-audit
- [ ] Verify no pop-ups on load
- [ ] Check content-to-ad ratio <30%
- [ ] Test mobile responsiveness
- [ ] Test on actual mobile device

**If rejected for "Policy Issues"**:
- [ ] Run policy-risk-scanner
- [ ] Zero Critical violations
- [ ] All affiliate disclosures in place
- [ ] Privacy policy complete
- [ ] Fact-check health/financial claims

**If rejected for "Technical Issues"**:
- [ ] Run technical-audit
- [ ] HTTPS enabled on all pages
- [ ] Sitemap valid and submitted
- [ ] No 404s on navigation
- [ ] Mobile-responsive with viewport tag

### Phase 3: Spot Checks (20 min)

Test each category manually:

**Content**:
- [ ] Read 3 random pages (not your best ones)
- [ ] Check they're valuable and original-sounding
- [ ] Verify metadata (title, description) are unique
- [ ] Check heading structure

**Technical**:
- [ ] Open site in browser
- [ ] Check HTTPS padlock
- [ ] Test homepage load time (<3 sec)
- [ ] Verify page loads on mobile
- [ ] Check no console errors

**UX**:
- [ ] Navigate site like first-time user
- [ ] Can you easily find about/contact?
- [ ] Any annoying pop-ups?
- [ ] Readable text sizes?
- [ ] Touch-friendly buttons on mobile?

**Policy**:
- [ ] Review privacy policy
- [ ] Spot-check affiliate disclosures (10 pages)
- [ ] Verify contact info works
- [ ] No obvious prohibited content

### Phase 4: Tool Verification (30 min)

Run all diagnostic tools:

```bash
# Full diagnostics
npm run ads-readiness-assessment
npm run content-audit
npm run technical-audit  
npm run ux-compliance-audit
npm run policy-risk-scanner

# Export results
npm run export-reports ./pre-resubmission/
```

**Review Results**:
- [ ] All audits show significant improvement from before
- [ ] Critical/High issues from original rejection are fixed
- [ ] No new Critical issues introduced
- [ ] Score trajectory is positive

---

## Pre-Resubmission Checklist

### Absolute Requirements (Must Pass)

- [ ] HTTPS enabled on all pages
- [ ] Minimum 3 pages with 300+ words each
- [ ] About page present (500+ words)
- [ ] Contact information available
- [ ] Privacy policy complete and accurate
- [ ] No full-screen pop-ups on page load
- [ ] Content readable without excessive ads
- [ ] No prohibited content (illegal, adult, hate speech, etc.)
- [ ] No misleading or deceptive claims
- [ ] Original, valuable content (not scraped)
- [ ] All internal links working
- [ ] No excessive keyword stuffing
- [ ] Affiliate disclosures clear and visible (if applicable)
- [ ] Mobile responsive with viewport tag

### Strong Recomm (Should Have)

- [ ] Content quality score ≥75/100
- [ ] No thin pages (<300 words) at scale
- [ ] Unique titles and meta descriptions on all pages
- [ ] Proper H1-H6 heading structure
- [ ] Core Web Vitals: LCP <2.5s, CLS <0.1
- [ ] Schema markup implemented
- [ ] Author credentials visible
- [ ] User reviews or testimonials
- [ ] Social proof (if applicable)

---

## Comparison Report

Create before/after comparison:

```markdown
# Resubmission Readiness Report

**Score Mode:** Core 79 + Profile
**Primary Site Type:** Blog

## Original Rejection Issues
1. Low-value content (thin pages)
2. Intrusive pop-ups
3. Missing contact information

## Status of Fixes

### Issue 1: Low-Value Content
- **Before**: 30% thin pages, average 180 words
- **After**: 5% thin pages, average 520 words
- **Audit Score**: 45/100 → 82/100
- **Status**: ✅ FIXED

### Issue 2: Intrusive Pop-ups
- **Before**: Full-screen overlay on load
- **After**: Delayed pop-up with clear close button
- **Manual Test**: ✅ PASSED

### Issue 3: Missing Contact
- **Before**: No contact info
- **After**: About page + Contact page + Email form
- **Manual Test**: ✅ PASSED

## Overall Readiness: ✅ READY FOR RESUBMISSION
- Critical Issues: 0
- High Issues: 0
- Medium Issues: 2 (acceptable)
- Score Improvement: +37 points

## Confidence Level: HIGH (85%+)
```

---

## Red Flags (Don't Resubmit Yet)

⚠️ **STOP** if any of these are true:

- [ ] Still have HTTPS disabled
- [ ] Content audit shows <50% improvement
- [ ] Policy issues still present (prohibited content)
- [ ] Pop-ups still showing on page load
- [ ] Still have >20% thin pages
- [ ] Technical audit shows new Critical issues
- [ ] Original rejection reason still apparent
- [ ] Major design is still broken on mobile
- [ ] Privacy policy is incomplete

**If any red flags present**: Go back to improvement guides and fix before resubmitting.

---

## Evidence Documentation

For transparency with Google, document your fixes:

```markdown
# Recovery Evidence

## Issue: Thin Pages (Original Rejection)

### Evidence of Fixes

#### Example Page 1: /blog/getting-started
- Before: 150 words
- After: 650 words
- URL: https://example.com/blog/getting-started
- Changes: Added step-by-step guide, FAQ, examples

#### Example Page 2: /guides/intro
- Before: 200 words
- After: 480 words
- URL: https://example.com/guides/intro
- Changes: Expanded with detailed explanations and examples

### Scope of Improvements
- 25 pages affected
- Average expansion: +320 words per page
- All now meet 300+ word minimum
- Content quality improved across all pages

### Measurement
- Content-audit before: 45/100
- Content-audit after: 82/100
- Improvement: +37 points (82%)
```

---

## Resubmission Checklist

Before clicking submit:

- [ ] All fixes documented
- [ ] All audits passing
- [ ] Manual spot-checks completed
- [ ] No new issues introduced
- [ ] Privacy policy updated and accurate
- [ ] Contact information verified working
- [ ] One more manual review (fresh eyes)
- [ ] Ready to submit

---

## Post-Resubmission Timeline

**0-3 Days**: Usually quick initial review by Google
**3-7 Days**: Full review period begins
**7-14 Days**: Decision typically made
**Up to 30 Days**: Possible extended review

Check email and Google Search Console regularly.

---

## If Re-Rejected

If rejected again:
1. Note the new reason carefully
2. Determine if it's the same issue or different
3. Run `rejection-root-cause-analysis` again
4. Consider `appeal-strategy-builder` if issue seems unfair
5. Create new `recovery-action-plan` for new issues

---

**Related Skills**:
- Analyze rejection → `rejection-root-cause-analysis`
- Create plan → `recovery-action-plan`
- Appeal (if disputing) → `appeal-strategy-builder`
