---
name: geo-localization-compliance
description: "Audit regional compliance requirements for publisher monetization across privacy law, disclosure expectations, language coverage, and restricted verticals."
---

# Geo Localization Compliance

Assess whether a site is ready to monetize across multiple jurisdictions with differing privacy, disclosure, consent, and restricted-content requirements.

## Quick Start

**Input**: Website URL, target countries, languages, consent setup, site type  
**Output**: Regional compliance matrix + localization gap list + priority fixes  
**Time**: 20-40 minutes

## Regions Covered

- European Union / EEA
- United States (state-level privacy emphasis)
- United Kingdom
- India
- Brazil
- Southeast Asia
- Other markets as applicable

## Review Areas

1. Privacy policy localization
2. Cookie consent and CMP implementation
3. Data rights disclosures
4. Language coverage and consistency
5. Region-specific restricted categories
6. Legal pages for commerce or subscriptions where applicable

## Output Contract

Return:
- `regions_reviewed`
- `compliance_status_by_region`
- `missing_requirements`
- `high_risk_locales`
- `priority_fixes`
- `related_arb_items`

## Typical Risk Signals

- English-only legal pages on multi-language sites
- No consent mechanism for EEA traffic
- Weak disclosures for affiliate or sponsored content in localized pages
- Different language versions with inconsistent policies
- Region-specific restricted products promoted without controls

## Routing

- If trust/legal pages are incomplete → `trust-credibility-strategy`
- If affiliate disclosures vary by locale → `affiliate-link-compliance`
- If the site spans premium networks → `multi-network-readiness`
