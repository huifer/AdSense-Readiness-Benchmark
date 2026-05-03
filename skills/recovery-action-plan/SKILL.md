---
name: recovery-action-plan
description: "Detailed week-by-week action plan to fix rejection issues. Includes task breakdown, timelines, dependencies, and verification steps for each fix."
---

# Recovery Action Plan

Create detailed week-by-week action plan for addressing rejection causes and preparing for resubmission.

## Scope Context

Meta-planning skill. Synthesizes findings from all audit skills into a prioritized, scoped action plan.

| Field | Value |
|---|---|
| **Phase** | Post-rejection planning |
| **Upstream** | `rejection-root-cause-analysis` |
| **ARB item coverage** | All pillars — scope determined by items flagged in root cause analysis |
| **Score mode** | Inherited from `rejection-root-cause-analysis`; the plan **must state** the score mode used |

The action plan output should include:
- `score_mode` from the originating audit
- `primary_site_type` to determine which extension profile applies
- Per-pillar task list tied to specific ARB item IDs

## Quick Start

**Input**: Root cause analysis (from `rejection-root-cause-analysis`)
**Output**: Week-by-week action plan + task breakdown + timelines
**Time**: 1-2 hours to plan, then 2-6 weeks to execute

## Planning Process

### Step 1: List All Issues

From root cause analysis, list every issue found:
1. [Issue 1] - Thin pages (CI01)
2. [Issue 2] - No HTTPS (TH01)
3. [Issue 3] - Intrusive pop-ups (UX03)
... etc

### Step 2: Group by Timeline

**Quick Wins** (<1 hour):
- Enable HTTPS
- Fix obvious broken links
- Remove pop-ups

**This Week** (1-8 hours):
- Add basic about/contact pages
- Create XML sitemap
- Implement affiliate disclosures

**Next 2 Weeks** (8-40 hours):
- Expand thin pages
- Improve content quality
- Fix UX issues

**3-6 Weeks** (40+ hours):
- Comprehensive content rewrite
- Design overhaul
- Complex technical fixes

### Step 3: Identify Dependencies

**Example**: Can't resubmit until:
1. HTTPS enabled (TH01)
2. Content expanded (CI01)
3. Pages passes audit (all criteria)

Map dependencies to prevent bottlenecks.

### Step 4: Create Week-by-Week Plan

---

## Sample Recovery Plan

### Week 1: Critical Foundations

**Monday-Tuesday: HTTPS & Technical (4 hours)**
- [ ] If not HTTPS, enable SSL certificate
- [ ] If on shared host, request HTTPS
- [ ] Test all pages redirect HTTP→HTTPS
- [ ] Verify no mixed content warnings

**Wednesday: Remove Intrusive Elements (2 hours)**
- [ ] Remove full-screen pop-ups
- [ ] Remove fake close buttons
- [ ] Remove misleading CTAs
- [ ] Move ads below fold

**Thursday-Friday: Basic Pages (6 hours)**
- [ ] Create about page (500+ words, with photo)
- [ ] Create contact page (contact form + email)
- [ ] Add author info to homepage
- [ ] Verify contact methods work

**Weekend: Verification**
- [ ] Manual test HTTPS
- [ ] Test navigation
- [ ] Check on mobile
- [ ] Verify pop-ups removed

---

### Week 2: Content Foundation

**Monday-Wednesday: Identify Issues (8 hours)**
- [ ] Run content-audit tool
- [ ] Identify all pages <300 words
- [ ] Identify duplicated content
- [ ] List pages to expand/rewrite

**Thursday-Friday: Expand Key Pages (8 hours)**
- [ ] Select 5-10 highest traffic thin pages
- [ ] Expand each to 400-600 words
- [ ] Add examples, details, FAQ
- [ ] Optimize titles/descriptions

**Weekend: Verification**
- [ ] Run content-audit again
- [ ] Compare before/after
- [ ] Verify quality improvements

---

### Week 3: Policy Compliance

**Monday: Affiliate Disclosures (2 hours)**
- [ ] Search site for affiliate links
- [ ] Add FTC disclosure to each page
- [ ] Verify disclosures are visible/conspicuous

**Tuesday: Privacy & Policies (4 hours)**
- [ ] Update/create privacy policy
- [ ] Add data deletion process
- [ ] Add GDPR compliance (if applicable)
- [ ] Add terms of service

**Wednesday: Content Review (6 hours)**
- [ ] Check for health misinformation (if applicable)
- [ ] Check for deceptive claims
- [ ] Fact-check all statistics
- [ ] Verify sources and citations

**Thursday-Friday: Continue Content (8 hours)**
- [ ] Expand more thin pages
- [ ] Remove duplicate content
- [ ] Add internal links

---

### Week 4: UX & Mobile

**Monday-Tuesday: Mobile Optimization (8 hours)**
- [ ] Add viewport meta tag
- [ ] Test on actual mobile devices
- [ ] Fix responsive design issues
- [ ] Optimize touch targets

**Wednesday: Color & Contrast (4 hours)**
- [ ] Test color contrast
- [ ] Fix text that doesn't meet WCAG AA
- [ ] Test with accessibility tools

**Thursday-Friday: Navigation & Links (6 hours)**
- [ ] Audit all internal links
- [ ] Fix 404 errors
- [ ] Improve navigation structure
- [ ] Add breadcrumbs where helpful

---

### Week 5-6: Final Polish & Verification

**Ongoing**:
- [ ] Continue expanding remaining thin pages
- [ ] Add images and multimedia
- [ ] Optimize remaining content

**Final Week**:
- [ ] Run full diagnostic (ads-readiness-assessment)
- [ ] Run all audit tools
- [ ] Manual verification
- [ ] Screenshot before/after
- [ ] Prepare resubmission evidence

---

## Action Plan Template

```markdown
# Recovery Action Plan

## Issue: [Issue Name]
- Root Cause: [Why it happened]
- Severity: [Critical/High/Medium]
- Effort: [Quick/Medium/Complex]
- Timeline: [1 day/1 week/2+ weeks]

## Tasks
1. [Task 1] - [Owner] - [Due Date]
   - [ ] Sub-task A
   - [ ] Sub-task B

2. [Task 2] - [Owner] - [Due Date]

## Dependencies
- [This task] requires [other task] to be done first
- [This task] blocks [other task]

## Verification
- [ ] Verify in tool: [ads-readiness-assessment]
- [ ] Manual test: [What to test]
- [ ] Success criteria: [What proves it's fixed]

## Timeline: [Total Days/Weeks]
```

---

## Common Fixes by Duration

**1 Day Fixes**:
- Remove pop-ups
- Fix robots.txt
- Add meta viewport
- Create about page
- Enable HTTPS (on managed hosts)

**1 Week Fixes**:
- Expand 5-10 thin pages
- Add affiliate disclosures
- Update privacy policy
- Fix mobile responsiveness
- Create contact page

**2 Week Fixes**:
- Expand all thin pages
- Remove all duplicates
- Fix UX issues
- Improve color/contrast
- Add all missing metadata

**3+ Week Fixes**:
- Comprehensive content rewrite
- Major design overhaul
- Technical infrastructure upgrade
- Complete SEO overhaul
- Systematic content quality improvement

---

## Prioritization Matrix

| Issue | Effort | Impact | Priority |
|-------|--------|--------|----------|
| No HTTPS | Quick | Critical | Do First |
| Pop-ups | Quick | Critical | Do First |
| Thin pages | Medium | High | Do Early |
| Missing contact | Quick | High | Do First |
| Duplicate content | Medium | High | Do Early |
| Color contrast | Medium | Medium | Do Later |
| Update frequency | Medium | Low | Do Last |

---

## Collaboration Template

For team-based projects:

```
Task: Expand thin pages
Owner: Content Team
Contributors: [Names]
Due: [Date]
Status: [Not Started / In Progress / Complete]
Evidence: [Links to completed work]
```

---

## Success Checklist

- [ ] All critical issues identified
- [ ] Action plan created
- [ ] Team aligned
- [ ] Timeline realistic
- [ ] Dependencies mapped
- [ ] Verification process clear
- [ ] Resources allocated
- [ ] Start date set

---

**Related Skills**:
- Analyze rejection → `rejection-root-cause-analysis`
- Verify before resubmit → `resubmission-readiness-check`
- Use improvement guides → content-improvement-blueprint, etc.
