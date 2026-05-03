---
name: multi-network-readiness
description: "Compare a site's readiness across multiple ad networks including AdSense, Ezoic, Mediavine, Raptive, and Amazon Publisher Services."
---

# Multi-Network Readiness

Assess whether a site is only AdSense-ready or also positioned for stronger monetization networks with different quality, traffic, and brand-safety thresholds.

## Quick Start

**Input**: Website URL, site type, geography, monthly traffic, primary traffic sources  
**Output**: Network-by-network readiness matrix + gap analysis + upgrade roadmap  
**Time**: 20-40 minutes

## Networks Covered

- Google AdSense
- Ezoic
- Mediavine
- Raptive
- Amazon Publisher Services (APS)

## Review Areas

1. Content quality and consistency
2. Traffic level and traffic source mix
3. Brand safety and advertiser suitability
4. UX and ad density tolerance
5. Trust signals and editorial maturity
6. Technical stability and performance

## Output Contract

Return a matrix with:
- `network`
- `eligibility_status`: ready / near_ready / not_ready / unknown
- `blocking_requirements`
- `score_gap`
- `estimated_time_to_eligibility`
- `highest_leverage_fixes`

## Typical Threshold Guidance

### AdSense
- Entry-level publisher acceptance
- Strong policy compliance required
- No fixed traffic threshold, but weak sites still fail

### Ezoic
- Lower traffic barrier than premium networks
- Strong technical integration tolerance needed
- Better fit for growth-stage publishers

### Mediavine
- Common rule of thumb: 50K+ sessions with stronger editorial quality
- High bar on brand safety, consistency, and audience quality

### Raptive
- Often 100K+ pageviews/session-equivalent benchmarks in practice
- High editorial and advertiser quality expectations

### APS
- Better fit for larger publishers with monetization operations maturity
- Requires stronger stability, scale, and operational sophistication

## Strategic Use

Use this skill to answer:
- Should this publisher apply only to AdSense now?
- Which network is the next step after AdSense?
- What fixes improve both approval odds and future RPM?

## Routing

- If traffic is below premium thresholds → `revenue-potential-estimator`
- If quality gaps are content-led → `content-improvement-blueprint`
- If trust and policy are the blockers → `trust-credibility-strategy`, `policy-remediation-plan`
- If multiple sites are being compared → `agency-batch-auditor`
