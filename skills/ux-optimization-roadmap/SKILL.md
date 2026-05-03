---
name: ux-optimization-roadmap
description: "Phased UX improvement plan with prioritized fixes for navigation, ad placement, typography, accessibility, and mobile optimization. Includes design recommendations and implementation timelines."
---

# UX Optimization Roadmap

Phased improvement plan for UX compliance violations. Prioritizes fixes by impact and effort, with design recommendations and implementation timelines.

## Scope Context

Downstream remediation skill fed by `ux-compliance-audit`.

| Field | Value |
|---|---|
| **Phase** | Remediation |
| **Upstream** | `ux-compliance-audit` |
| **ARB items addressed** | UX01–UX15 (core); UX16–UX18 when flagged as extension |
| **Score mode** | Inherited from `ux-compliance-audit` output — this skill does not independently score |

Fixes must be re-verified by running `ux-compliance-audit` again under the **same score mode**.

## Purpose

Fix UX issues and create compliant, user-friendly experience:
- Clear navigation and site structure
- Appropriate content-to-ad ratio
- Readable typography and layout
- Accessibility (WCAG AA) compliance
- Mobile optimization

## Prioritized Implementation Phases

### Phase 1: Critical Fixes (Week 1-2) — Do First

**Remove Intrusive Interstitials (UX03)**
- Full-screen popups on load: Remove or make easily dismissible
- Modal windows: Add visible close button (actual X, not fake)
- Overlay ads: Move below fold or delay appearance
- Impact: Automatic rejection if intrusive

**Fix Content-to-Ad Ratio (UX02)**
- Measure: Ads should occupy <30% of viewport
- Action: Remove/relocate ads if excessive
- Before: 50% ads visible → After: 25% ads visible
- Timeline: 2-4 hours
- Impact: Blocks approval

**Fix Deceptive UI (UX06)**
- Remove fake close buttons
- Remove fake download buttons
- Fix misleading CTAs
- Timeline: 1-2 hours
- Impact: High rejection risk

### Phase 2: Accessibility (Week 2-3) — Do Next

**Color Contrast (UX11)**
- Audit: All text colors with contrast checker
- Target: ≥4.5:1 normal, ≥3:1 large text
- Fix: Adjust colors or backgrounds
- Timeline: 2-4 hours
- Tools: WAVE, WebAIM Contrast Checker
- Priority: HIGH

**Image Alt Text (UX12)**
- Add descriptions to informative images
- Decorative images: use alt=""
- Timeline: 2-6 hours depending on image count
- Example: alt="Apple pie cooling on windowsill"

**Keyboard Navigation**
- Test: Tab through page with keyboard only
- Fix: Add focus indicators, make interactive elements accessible
- Timeline: 4-8 hours

### Phase 3: Typography & Readability (Week 3-4) — Important

**Font Size (UX04)**
- Body text: Increase to ≥14px (16px ideal)
- Headings: Scale appropriately
- Before: 12px → After: 16px
- Benefit: 20-30% improvement in readability
- Timeline: 1-2 hours for whole site

**Line Height & Spacing**
- Line-height: 1.4-1.8 (1.6 recommended)
- Paragraph spacing: 1-1.5em between paragraphs
- Letter spacing: 0.02-0.05em for headings
- Before: cramped → After: spacious, readable
- Timeline: 1-2 hours

**Font Choice**
- Body: Sans-serif (Open Sans, Inter, Roboto)
- Headings: Bolder serif or sans-serif
- Avoid: Decorative fonts for body text, excessive thin fonts
- Timeline: 30 min - 1 hour

### Phase 4: Navigation & Structure (Week 4-5) — Ongoing

**Navigation Menu (UX01)**
- Visible on all pages
- Includes main categories
- Mobile menu functional (hamburger)
- Sticky or easy-access
- Timeline: 2-4 hours to redesign

**Internal Linking (UX05)**
- Every page within 3 clicks of homepage
- No orphan pages
- Breadcrumbs helpful
- Related content links
- Timeline: 1-2 hours for whole site

**Search Functionality (UX10)**
- If >30 pages: Add search box
- Results relevant and complete
- Timeline: 4-8 hours to implement

### Phase 5: Mobile Optimization (Week 5-6) — Essential

**Responsive Design (UX14)**
- Viewport meta tag: `<meta name="viewport" content="width=device-width">`
- Test at 320px, 768px, 1024px, 1440px
- Touch targets: ≥48×48px
- Timeline: 4-12 hours depending on site

**Mobile Menu**
- Hamburger menu functional
- Easy to open/close
- Full navigation accessible
- Timeline: 2-4 hours

**Mobile Typography**
- Text readable without zooming
- Proper spacing on mobile
- Tap targets not too close
- Timeline: 1-2 hours

**Mobile Ads**
- Not covering content when tapped
- Easy to close
- Appropriate ad density for mobile
- Timeline: 2-4 hours

### Phase 6: Browser Compatibility (Week 6+) — Final

**Test Across Browsers**
- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)
- Timeline: 1-2 hours testing, then fixes as needed

**Test Across Devices**
- Desktop (1920px, 1440px)
- Tablet (768px)
- Mobile (375px, 414px)
- Timeline: 1-2 hours testing

---

## Design Recommendations

### Navigation Layout

**Option A: Horizontal Menu**
```
┌─────────────────────────────────────┐
│ Logo │ Home │ About │ Services │ Contact │
└─────────────────────────────────────┘
```
**When**: Fewer than 5 main categories

**Option B: Sticky Header**
```
Navigation stays visible when scrolling
(Better for user reference)
```

**Option C: Mobile Hamburger**
```
For mobile: ☰ → Menu drops down on click
Must be easily closeable
```

### Ad Placement Best Practices

**Recommended**: Above fold, sidebar, after content
**Avoid**: Between paragraphs (intrusive), before navigation
**Max Density**: 3 units per page (excluding auto-ads)
**Ad Label**: "Advertisement" clearly visible

### Accessibility Checklist

- [ ] All images have alt text
- [ ] Color contrast ≥4.5:1
- [ ] Keyboard navigation works
- [ ] Screen reader compatible
- [ ] Focus indicators visible
- [ ] Form labels associated with inputs
- [ ] Error messages clear and helpful
- [ ] Links descriptive (not "click here")
- [ ] ARIA labels where needed
- [ ] Heading hierarchy correct

### Mobile-First CSS Pattern

```css
/* Mobile first (base styles) */
body { font-size: 16px; }
.container { width: 100%; padding: 1rem; }
.nav { display: none; } /* Hidden by default */

/* Tablet and up */
@media (min-width: 768px) {
    .container { width: 750px; margin: 0 auto; }
    .nav { display: block; }
}

/* Desktop and up */
@media (min-width: 1024px) {
    .container { width: 960px; }
}
```

---

## Implementation Timeline

**Quick (1-2 weeks)**: Critical + Accessibility
**Medium (3-4 weeks)**: + Typography + Navigation
**Comprehensive (6-8 weeks)**: + Mobile + Browser testing

---

## Testing Checklist

- [ ] Mobile-Friendly Test (Google)
- [ ] Lighthouse Audit (Chrome)
- [ ] WAVE Accessibility Scan
- [ ] Color Contrast Check (all text)
- [ ] Keyboard Navigation (full site)
- [ ] Cross-browser test (Chrome, Firefox, Safari)
- [ ] Cross-device test (mobile, tablet, desktop)
- [ ] Ad placement review
- [ ] Navigation walkthrough
- [ ] Link integrity check

---

**Related Skills**:
- Audit results → `ux-compliance-audit`
- Verify fixes → `resubmission-readiness-check`
