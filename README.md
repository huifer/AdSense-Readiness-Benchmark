# ARB — Publisher Monetization Readiness Platform

[![Policy-First](https://img.shields.io/badge/Policy--First-1f6feb)](#why-arb)
[![Documentation-First](https://img.shields.io/badge/Documentation--First-0f766e)](#repository-structure)
[![Bilingual](https://img.shields.io/badge/Bilingual-English%20%7C%20%E4%B8%AD%E6%96%87-8b5cf6)](./readme.zh.md)
[![Primary-Focus](https://img.shields.io/badge/Primary%20Focus-AdSense%20Readiness-f59e0b)](#what-arb-does)
[![Coverage](https://img.shields.io/badge/Coverage-Core%2079%20%7C%20Full%20105-374151)](#scoring-scope)
[![skills.sh](https://skills.sh/b/huifer/AdSense-Readiness-Benchmark)](https://skills.sh/huifer/AdSense-Readiness-Benchmark)

English | [中文说明](./readme.zh.md)

ARB is a documentation-first audit framework for evaluating whether a website is ready for AdSense review and broader publisher monetization. It combines a benchmark model, a fixed scoring contract, and a 26-skill workflow that covers diagnosis, remediation, verification, monitoring, and recovery.

The framework is built around 6 pillars, a fixed Core 79 review set for baseline checks, optional extension coverage up to the full 105-item benchmark, and hard veto rules so critical risks are never hidden by an average score.

## What ARB Does

- Standardizes publisher-readiness reviews into evidence-backed checks.
- Routes users through a full workflow from first audit to resubmission readiness.
- Supports both fast triage and full-scope audits.
- Produces structured outputs that are easy to reuse in reports, remediation plans, and follow-up reviews.
- Extends beyond AdSense into multi-network readiness, benchmark comparison, and revenue-priority analysis when needed.

## Who This Is For

- Site owners preparing for an initial AdSense application.
- Operators trying to reduce rejection risk before resubmission.
- Consultants or agencies auditing multiple publisher sites.
- Teams that need a repeatable audit contract instead of ad hoc reviews.

## Why ARB

ARB is designed around three constraints:

1. High-risk policy failures must stop the process early.
2. Audit outputs must be reproducible and evidence-based.
3. Different site types need different emphasis without changing the base scoring contract.

That is why ARB uses:

- 4 review gates.
- 6 scoring pillars: CI, PC, TH, UX, TD, SI.
- 3 score modes: Core 79, Core 79 + Profile, Full 105.
- Veto precedence for critical failures.

## Repository Structure

| Path | Purpose |
|------|---------|
| [ARB-benchmark.md](ARB-benchmark.md) | Source of truth for all item definitions, scoring rules, site-type profiles, and report expectations |
| [skills/README.md](skills/README.md) | Full skill map and routing guide |
| [skills/arb-full-audit/SKILL.md](skills/arb-full-audit/SKILL.md) | Single best starting point for most users |
| [AGENTS.md](AGENTS.md) | Contributor and agent quality rules |
| [skills/](skills/) | Individual audit, remediation, monitoring, and recovery skills |

## Core Concepts

### 1. Six Pillars

| Code | Pillar | Focus |
|------|--------|-------|
| CI | Content Integrity | Originality, depth, structure, freshness |
| PC | Policy Compliance | Prohibited content, disclosure, data rights |
| TH | Technical Health | HTTPS, performance, crawlability, markup |
| UX | User Experience | Navigation, readability, accessibility, ad safety |
| TD | Trust & Disclosure | Legal pages, identity, business trust, editorial trust |
| SI | Search Integrity | Spam prevention, linking hygiene, SEO legitimacy |

### 2. Scoring Scope

| Mode | Use When | Coverage |
|------|----------|----------|
| `Core 79` | Fast baseline triage | Fixed baseline item set only |
| `Core 79 + Profile` | Standard single-site audit | Core 79 plus one site-type profile and triggered items |
| `Full 105` | Mixed-model or client-facing audit | Full benchmark coverage |

### 3. Veto Rules

Readiness cannot pass if critical blockers fail. At minimum, treat the following as hard-stop conditions:

- TH01: HTTPS not enabled site-wide
- TD01: no privacy policy
- Any unresolved fail in PC items
- Any conflict on affiliate disclosure that cannot be cleared with evidence

See [ARB-benchmark.md](ARB-benchmark.md) for the detailed veto contract.

## Full Usage Guide

### Prerequisites

This repository is documentation-first. It does not ship a standalone CLI or bundled checker runtime. You use it by opening and following the benchmark and skill documents inside your editor or agent environment.

Recommended setup:

- A Markdown-capable editor such as VS Code
- Access to the target site URL, source files, or both
- A way to capture evidence such as screenshots, page links, crawl notes, or extracted findings

### Fastest Start

From the repository root:

```bash
open ./skills/arb-full-audit/SKILL.md
open ./ARB-benchmark.md
open ./skills/README.md
```

If you only want a lightweight triage instead of the full workflow:

```bash
open ./skills/ads-readiness-assessment/SKILL.md
```

### Standard Workflow

Use this path for most audits:

1. Define the site URL, site type, and desired score mode.
2. Start with [skills/arb-full-audit/SKILL.md](skills/arb-full-audit/SKILL.md).
3. Run Gate 1 technical checks.
4. Run Gate 2 content, policy, spam, and copyright checks.
5. Run Gate 3 trust, UX, and disclosure checks.
6. Aggregate scores, apply veto logic, and record top fixes.
7. Use the matching remediation skills.
8. Finish with [skills/resubmission-readiness-check/SKILL.md](skills/resubmission-readiness-check/SKILL.md).

### Manual Gate-by-Gate Workflow

Use this when you want more control over each phase.

| Gate | Goal | Main Skills |
|------|------|-------------|
| Gate 1 | Technical baseline | `technical-audit` |
| Gate 2 | Content, policy, and spam risk | `ads-readiness-assessment`, `content-audit`, `policy-risk-scanner`, `seo-spam-detection`, `copyright-ip-check` |
| Gate 3 | Trust, UX, and disclosure | `ux-compliance-audit`, `trust-credibility-strategy`, `affiliate-link-compliance` |
| Gate 4 | Remediation and final verification | `content-improvement-blueprint`, `technical-remediation-guide`, `ux-optimization-roadmap`, `policy-remediation-plan`, `resubmission-readiness-check` |

### Choose the Right Entry Point

| Situation | Start Here |
|-----------|------------|
| First full audit | `arb-full-audit` |
| Fast initial diagnosis | `ads-readiness-assessment` |
| Technical blockers first | `technical-audit` |
| Affiliate-heavy site | `affiliate-link-compliance` |
| Rejection analysis | `rejection-root-cause-analysis` |
| Post-approval monitoring | `active-compliance-monitor` |
| Agency portfolio workflow | `agency-batch-auditor` |

### Inputs You Should Prepare

For the best result, gather these before you start:

| Input | Required | Notes |
|------|----------|-------|
| Site URL | Usually yes | Full URL including scheme |
| Site type | Yes for scoring | blog, tool, affiliate, news, ecommerce, forum |
| Score mode | Recommended | `Core 79`, `Core 79 + Profile`, or `Full 105` |
| Traffic tier | Optional | Useful for benchmarking and revenue overlays |
| Target networks | Optional | Use when evaluating beyond AdSense |
| Evidence pack | Strongly recommended | Screenshots, URLs, examples, crawl observations |

### Supported Review Modes

Most skills can be used in one of these ways:

- URL mode: review the live site.
- Source mode: inspect local project files.
- Manual mode: follow the checklist and record findings yourself.

See [skills/README.md](skills/README.md) for the skill-by-skill mode matrix.

## Outputs You Should Expect

A complete audit should normally produce:

- A declared score mode and evaluated scope
- Pillar scores for CI, PC, TH, UX, TD, and SI
- Veto status and any stop conditions
- Evidence-backed findings for non-pass items
- A prioritized fix list
- Suggested next skills
- Optional approval probability and network-gap overlays

Recommended artifact set:

| Artifact | Why It Matters |
|----------|----------------|
| Markdown audit report | Easy to review and share |
| JSON scorecard | Easier aggregation and comparison |
| Evidence notes | Supports reproducibility |
| Remediation plan | Turns findings into action |

## Typical User Paths

### Website Owner

1. Start with `arb-full-audit`.
2. Fix the highest-priority blockers.
3. Run `resubmission-readiness-check`.
4. Submit only after all veto-adjacent issues are resolved.

### Consultant or Agency

1. Use `agency-batch-auditor` for multi-site intake.
2. Use `arb-full-audit` for deep reviews on selected sites.
3. Convert findings into client remediation tracks.
4. Re-run targeted checks before delivery or resubmission.

### Rejected Publisher

1. Start with `rejection-root-cause-analysis`.
2. Build the fix sequence with `recovery-action-plan`.
3. Run the remediation skills that match the failing pillars.
4. Finish with `resubmission-readiness-check`.

## Skill Groups

### Orchestration

- `arb-full-audit`

### Diagnostics

- `ads-readiness-assessment`
- `content-audit`
- `technical-audit`
- `ux-compliance-audit`
- `policy-risk-scanner`

### Remediation

- `content-improvement-blueprint`
- `technical-remediation-guide`
- `ux-optimization-roadmap`
- `policy-remediation-plan`
- `trust-credibility-strategy`

### Cross-Phase Checks

- `affiliate-link-compliance`
- `copyright-ip-check`
- `seo-spam-detection`

### Monitoring and Recovery

- `active-compliance-monitor`
- `health-check-automation`
- `alert-rules-setup`
- `rejection-root-cause-analysis`
- `recovery-action-plan`
- `appeal-strategy-builder`
- `resubmission-readiness-check`

### Scale and Monetization Overlays

- `ai-content-compliance`
- `multi-network-readiness`
- `revenue-potential-estimator`
- `geo-localization-compliance`
- `competitive-benchmark`
- `agency-batch-auditor`

## Recommended Reading Order

If you are new to the repository, read in this order:

1. [README.md](README.md)
2. [ARB-benchmark.md](ARB-benchmark.md)
3. [skills/README.md](skills/README.md)
4. [skills/arb-full-audit/SKILL.md](skills/arb-full-audit/SKILL.md)
5. The specific skill docs you plan to run

## Working Rules

When using or extending ARB, keep these rules intact:

- Do not invent evidence.
- Do not suppress veto signals.
- Do not change score scope without naming it explicitly.
- Do not mark a site ready just because the weighted score is high.
- Do keep findings reproducible and traceable.

The detailed contributor contract lives in [AGENTS.md](AGENTS.md).

## FAQ

### Is this a software product or a documentation framework?

It is a documentation-first framework. The repository defines the benchmark, scoring model, skill flow, and output expectations.

### Can I use it without evaluating all 105 items?

Yes. Start with `Core 79` or `Core 79 + Profile` when you need a faster or more targeted review.

### Should I always start with `arb-full-audit`?

For most users, yes. Use a specialist skill first only when you already know the problem area.

### Does a high score guarantee approval?

No. ARB is a risk-reduction framework, not an official approval predictor.

## Related Documents

- [ARB-benchmark.md](ARB-benchmark.md)
- [skills/README.md](skills/README.md)
- [skills/arb-full-audit/SKILL.md](skills/arb-full-audit/SKILL.md)
- [readme.zh.md](readme.zh.md)

