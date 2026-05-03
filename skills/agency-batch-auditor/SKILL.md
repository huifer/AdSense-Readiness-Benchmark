---
name: agency-batch-auditor
description: "Run ARB-style audits across multiple sites, normalize results, rank client opportunities, and produce white-label delivery outputs for agencies and consultants."
---

# Agency Batch Auditor

Evaluate multiple publisher sites in one operating workflow so agencies, consultants, and portfolio owners can rank opportunities and deliver standardized reports.

## Quick Start

**Input**: Multiple URLs, client names, site types, traffic tiers, target networks  
**Output**: Batch score matrix + opportunity ranking + white-label summary format  
**Time**: Depends on portfolio size

## Best For

- Agencies managing 5-100 publisher properties
- Consultants prioritizing which client to fix first
- Portfolio teams comparing monetization readiness across sites

## Output Contract

Return:
- `portfolio_summary`
- `site_rankings`
- `highest_priority_clients`
- `cross_site_pattern_findings`
- `white_label_report_sections`
- `recommended_next_actions_by_site`

## Evaluation Logic

For each site:
1. Run `arb-full-audit` or `ads-readiness-assessment`
2. Normalize score mode and metadata
3. Compare veto counts, pillar weaknesses, and remediation effort
4. Rank sites by likely payoff and time-to-readiness

## Recommended Ranking Factors

- Approval proximity
- Revenue upside
- Ease of remediation
- Strategic client importance
- Cross-network eligibility potential

## White-Label Delivery

Suggested report sections:
- Executive summary
- Readiness scorecard
- Critical blockers
- 30/60/90-day fix roadmap
- Monetization upside summary
- Recommended next skill or service package

## Routing

- For market comparison → `competitive-benchmark`
- For revenue prioritization → `revenue-potential-estimator`
- For premium network targeting → `multi-network-readiness`
