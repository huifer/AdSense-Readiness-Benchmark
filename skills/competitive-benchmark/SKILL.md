---
name: competitive-benchmark
description: "Benchmark a site against comparable publishers by vertical, traffic tier, trust signals, and monetization readiness."
---

# Competitive Benchmark

Place a site's ARB score and monetization readiness in market context by comparing it to typical performance patterns for similar publishers.

## Quick Start

**Input**: Site URL, primary competitors, vertical, traffic tier, ARB score if available  
**Output**: Benchmark delta report + gap heatmap + catch-up priorities  
**Time**: 20-45 minutes

## What This Adds

Absolute scores are useful, but not enough. This skill answers:
- How does this site compare to the category median?
- Which trust, content, or UX signals are below market expectations?
- Which improvements close the most competitive gap fastest?

## Benchmark Dimensions

1. Content depth and consistency
2. Trust and editorial signals
3. UX clarity and ad readiness
4. Technical hygiene and speed
5. Search integrity and spam avoidance
6. Monetization maturity

## Output Contract

Return:
- `benchmark_cohort`
- `site_vs_median`
- `top_gaps`
- `quick_win_fixes`
- `structural_gaps`
- `market_position_summary`

## Recommended Use

Use after `arb-full-audit` or `ads-readiness-assessment` when stakeholders need market context for prioritization, investment, or roadmap planning.

## Routing

- If economics matter more than score context → `revenue-potential-estimator`
- If multiple client sites are compared → `agency-batch-auditor`
- If weak areas cluster in one pillar → route to the corresponding remediation skill
