---
name: revenue-potential-estimator
description: "Estimate monetization potential using traffic, geography, content vertical, ad network fit, and readiness score to model RPM and growth upside."
---

# Revenue Potential Estimator

Translate readiness and site quality into monetization potential, so users understand not only whether a site can qualify, but what the business upside looks like after fixes.

## Quick Start

**Input**: Site URL, traffic estimates, geo mix, traffic source mix, site type, ARB score if available  
**Output**: RPM/CPM benchmark range + revenue scenarios + highest-ROI fixes  
**Time**: 15-30 minutes

## Use Cases

- Forecast whether remediation effort is commercially justified
- Compare monetization upside by network and geography
- Prioritize fixes that improve both approval likelihood and RPM

## Inputs

Preferred inputs:
- Monthly sessions or users
- Top geographies
- Primary traffic sources
- Main content vertical
- Current ad network or target networks
- ARB score / pillar scores if already audited

## Output Contract

Return:
- `baseline_revenue_range`
- `post_fix_revenue_range`
- `benchmark_rpm_range`
- `key_drivers`
- `highest_roi_fixes`
- `network_comparison`
- `confidence_notes`

## Model Logic

Estimate revenue across three layers:

1. **Audience quality**
- GEO mix
- Organic vs social vs direct traffic
- Returning visitor quality

2. **Inventory quality**
- Content depth
- Page speed
- Layout and ad-viewability potential
- Advertiser-safe environment

3. **Network fit**
- AdSense baseline fit
- Premium network upside if quality and traffic qualify

## Reporting Guidance

Always state estimates as ranges, not exact values.
Use explicit caveats when traffic data is missing or external tools are required.
Do not imply guaranteed earnings.

## Routing

- If network selection is unclear → `multi-network-readiness`
- If approval risk dominates economics → `arb-full-audit`
- If vertical-specific benchmarking is needed → `competitive-benchmark`
