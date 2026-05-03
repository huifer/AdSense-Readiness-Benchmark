---
name: arb-full-audit
description: "Unified orchestrator for the complete ARB lifecycle. Accepts a URL + site type and automatically routes through all 4 Gates in sequence, halting at any veto condition. Produces a single consolidated report with score, grade, veto alerts, approval probability, and prioritized fix list."
---

# ARB Full Audit — Unified Orchestrator

Single entry point that runs the entire ARB evaluation pipeline end-to-end. Replaces manual skill sequencing for users who want a complete audit in one invocation.

## Quick Start

**Input**: Website URL + site type + optional score mode  
**Output**: Consolidated Markdown report + JSON scorecard + prioritized fix list + approval probability  
**Time**: 45–90 minutes for full 105-item pass

## Required Inputs

| Field | Required | Default | Notes |
|-------|----------|---------|-------|
| `url` | Yes | — | Full URL including scheme (https://) |
| `site_type` | Yes | — | blog / tool / affiliate / news / ecommerce / forum |
| `score_mode` | No | `Core 79 + Profile` | `Core 79` / `Core 79 + Profile` / `Full 105` |
| `traffic_tier` | No | `unknown` | starter (<1K UV/mo) / growth (1K–50K) / scale (50K+) |
| `target_networks` | No | `adsense` | Comma-separated: adsense, ezoic, mediavine, raptive, aps |

## Output Contract

Every arb-full-audit run must declare:

```json
{
  "meta": {
    "url": "<evaluated URL>",
    "site_type": "<declared type>",
    "score_mode": "<Core 79 | Core 79 + Profile | Full 105>",
    "traffic_tier": "<starter | growth | scale | unknown>",
    "evaluated_item_count": 0,
    "selected_profile_items": [],
    "triggered_extension_items": [],
    "timestamp": "<ISO 8601>",
    "arb_version": "3.0"
  },
  "scores": {
    "CI": { "score": 0, "max": 0, "pct": 0 },
    "PC": { "score": 0, "max": 0, "pct": 0 },
    "TH": { "score": 0, "max": 0, "pct": 0 },
    "UX": { "score": 0, "max": 0, "pct": 0 },
    "TD": { "score": 0, "max": 0, "pct": 0 },
    "SI": { "score": 0, "max": 0, "pct": 0 },
    "total_weighted": 0,
    "grade": "<Ready | Minor Fixes | Significant Work | Major Overhaul | Not Ready>"
  },
  "veto": {
    "triggered": false,
    "items": [],
    "gate_stopped_at": null
  },
  "approval_probability": {
    "estimate": "<high | medium | low | very_low>",
    "pct_range": "<e.g. 60–80%>",
    "confidence": "<statistical estimate — not an official Google signal>",
    "primary_risk_factors": []
  },
  "findings": [],
  "top_fixes": [],
  "network_gaps": {},
  "next_skills": []
}
```

> **Approval probability is a statistical estimate based on score ranges and common rejection patterns. It is not an official signal from Google or any ad network.**

## Gate Execution Flow

```
Input: URL + site_type + score_mode
  │
  ▼
┌─────────────────────────────────┐
│  GATE 1 — Technical Baseline    │  ← technical-audit (TH01–TH20)
│  Skill: technical-audit         │
└────────────────┬────────────────┘
                 │
         TH01 (HTTPS) fail?
         ┌───── YES ─────────────────→ STOP: emit veto report
         │                              reason: TH01 — HTTPS disabled
         NO
         ▼
┌─────────────────────────────────┐
│  GATE 2 — Content, Policy,      │  ← ads-readiness-assessment
│           Spam & Copyright      │    content-audit (CI01–CI18)
│                                 │    policy-risk-scanner (PC01–PC13)
│                                 │    seo-spam-detection (SI01–SI16)
│                                 │    copyright-ip-check (CI/PC cross)
└────────────────┬────────────────┘
                 │
         Any PC01–PC13 fail?
         ┌───── YES ─────────────────→ STOP: emit veto report
         │                              reason: PC veto — list items
         NO
         ▼
┌─────────────────────────────────┐
│  GATE 3 — Trust, UX,            │  ← ux-compliance-audit (UX01–UX18)
│           Disclosures           │    trust-credibility-strategy (TD01–TD20)
│                                 │    affiliate-link-compliance (PC10/TD cross)
└────────────────┬────────────────┘
                 │
         TD01 (Privacy Policy) fail?
         ┌───── YES ─────────────────→ STOP: emit veto report
         │                              reason: TD01 — no privacy policy
         NO
         ▼
┌─────────────────────────────────┐
│  GATE 4 — Score & Report        │  ← Aggregate all pillar scores
│                                 │    Apply site-type weights
│                                 │    Compute grade + approval_probability
│                                 │    Generate top_fixes list
│                                 │    Invoke network gap analysis (if
│                                 │    target_networks specified)
└────────────────┬────────────────┘
                 │
                 ▼
         Full consolidated report
```

## Step-by-Step Execution

### Step 1: Collect Inputs

Confirm with the user:

- Site URL (required)
- Site type (required): blog / tool / affiliate / news / ecommerce / forum
- Score mode (default: Core 79 + Profile)
- Traffic tier (optional but improves benchmarking)
- Target ad networks beyond AdSense (optional; triggers multi-network-readiness overlay)

If any required input is missing, pause and request it before proceeding. Do not assume defaults silently.

### Step 2: Declare Scope

Before running any evaluation, emit the scope header:

```
## ARB Audit Scope
- URL: <url>
- Site Type: <type>
- Score Mode: <mode>
- Core Items: 79
- Profile Extension Items: <n> (<profile name>)
- Conditional Trigger Items: <n> (list triggers)
- Total Evaluated Items: <sum>
- Traffic Tier: <tier>
- Target Networks: <list>
```

### Step 3: Run Gate 1 — Technical Baseline

Execute technical-audit across all TH01–TH20 items.

**Veto check after Gate 1:**
- If TH01 = Fail → immediately halt, emit veto report, do NOT proceed to Gate 2
- Note any TH items that are Fail/Partial for the final report

### Step 4: Run Gate 2 — Content, Policy, Spam, Copyright

Execute in parallel where evidence allows:
- `content-audit` → CI01–CI18
- `policy-risk-scanner` → PC01–PC13
- `seo-spam-detection` → SI01–SI16
- `copyright-ip-check` → CI/PC cross-items

**Veto check after Gate 2:**
- If any PC01–PC13 = Fail → halt, emit veto report listing all failing PC items
- Continue only when all PC items are Pass or Partial (Partial PC items must be flagged as high-priority in the final report)

### Step 5: Run Gate 3 — Trust, UX, Disclosures

Execute:
- `ux-compliance-audit` → UX01–UX18
- `trust-credibility-strategy` → TD01–TD20
- `affiliate-link-compliance` → PC10/TD cross-items

**Veto check after Gate 3:**
- If TD01 = Fail → halt, emit veto report
- Record all TD and UX Fail/Partial items

### Step 6: Aggregate Scores & Generate Report

Apply site-type weighted scoring per ARB-benchmark.md Part 3:

1. For each pillar: `pillar_score = (sum of item scores / max possible) × 100`
2. For total: `total = Σ(pillar_score × pillar_weight[site_type])`
3. Assign grade from threshold table
4. Compute `approval_probability` estimate (see table below)
5. Generate `top_fixes` — top 10 items by: `severity × (pillar_weight × item_gap)`
6. If `target_networks` is set, invoke `multi-network-readiness` overlay

**Approval Probability Table** *(statistical estimate, not an official signal)*:

| Total Score | Estimate | Pct Range | Notes |
|-------------|----------|-----------|-------|
| 90–100 | high | 80–92% | Remaining risk mainly geo/niche restrictions |
| 75–89 | medium | 55–75% | Fix all Partial veto-adjacent items before submitting |
| 60–74 | low | 25–50% | Systematic fixes needed across 2–3 pillars |
| 40–59 | very_low | 8–22% | Major overhaul required |
| 0–39 | very_low | <8% | Not ready; complete Phase 1 remediation first |

### Step 7: Route to Next Skills

Based on results, emit `next_skills` array with context:

| Condition | Recommended skill |
|-----------|-------------------|
| CI score < 70 | `content-improvement-blueprint` |
| TH score < 70 | `technical-remediation-guide` |
| UX score < 70 | `ux-optimization-roadmap` |
| PC any Fail/Partial | `policy-remediation-plan` |
| TD score < 70 | `trust-credibility-strategy` |
| SI score < 70 | `seo-spam-detection` → `content-improvement-blueprint` |
| All ≥ 75 | `resubmission-readiness-check` |
| Rejection history | `rejection-root-cause-analysis` |
| multi-network target | `multi-network-readiness` |
| AI content suspected | `ai-content-compliance` |
| Traffic tier = scale | `geo-localization-compliance`, `competitive-benchmark` |
| Agency context | `agency-batch-auditor` |

## Veto Report Format

When a gate veto fires, emit this structure and stop:

```markdown
# ⛔ ARB Audit Halted — Veto Condition

**Gate**: <Gate number and name>
**Veto Item(s)**: <item IDs>
**Reason**: <plain-language explanation>

## What This Means

<1–2 sentences on why this is a hard blocker>

## Required Fix

<Specific, actionable fix steps>

## Estimated Time to Resolve

<Time estimate>

## Next Step After Fix

Re-run `arb-full-audit` from Gate 1 once the veto condition is resolved.
Do not proceed to subsequent gates before fixing the veto item(s).
```

## Consolidated Report Format

When all gates pass, emit the full report:

```markdown
# ARB Full Audit Report

**Site**: <url>  
**Date**: <ISO date>  
**Site Type**: <type>  
**Score Mode**: <mode>  
**ARB Version**: 3.0  

---

## Scorecard

| Pillar | Score | Max | % | Weight | Weighted |
|--------|-------|-----|---|--------|---------|
| CI – Content Integrity | | | | | |
| PC – Policy Compliance | | | | | |
| TH – Technical Health | | | | | |
| UX – User Experience | | | | | |
| TD – Trust & Disclosure | | | | | |
| SI – Search Integrity | | | | | |
| **TOTAL** | | | | | **XX.X** |

**Grade**: <grade>  
**Approval Probability**: <estimate> (<pct_range>) — *statistical estimate, not an official signal*

---

## Veto Status

✅ No veto conditions triggered.
*or*
⛔ Veto triggered at Gate N: <items>

---

## Top 10 Priority Fixes

| Priority | Item | Pillar | Severity | Est. Effort |
|----------|------|--------|----------|-------------|
| 1 | | | | |
...

---

## Full Findings by Pillar

### Content Integrity (CI)
<findings table with status per item>

### Policy Compliance (PC)
<findings table>

### Technical Health (TH)
<findings table>

### User Experience (UX)
<findings table>

### Trust & Disclosure (TD)
<findings table>

### Search Integrity (SI)
<findings table>

---

## Network Readiness (if applicable)

<multi-network-readiness overlay when target_networks specified>

---

## Approval Probability Detail

<breakdown of risk factors>

---

## Recommended Next Skills

<next_skills with rationale>

---

## Audit Metadata

- Evaluated items: <n>
- Profile extension items: <list>
- Conditional trigger items: <list>
- Score mode: <mode>
- Traffic tier: <tier>
```

## Scoring Mode Rules (Inherited from ARB-benchmark.md)

- Never mix items from different score modes without documenting it
- If the site is multi-model, escalate to `Full 105` and document this
- Core 79 mode disables profile and conditional extension items
- `Full 105` evaluates all 105 items regardless of site type

## Quality Constraints (Inherited from AGENTS.md)

1. Do not invent evidence — every finding requires an observable artifact
2. Do not infer Pass without data — prefer Partial + manual-review note
3. Veto precedence is absolute — a high total score cannot override a veto item
4. Score mode must be declared and match the actual evaluated item set
5. `approval_probability` must always carry its disclaimer in output

## Checklist

1. ✓ Inputs collected and scope declared
2. ✓ Gate 1 complete — TH veto check passed
3. ✓ Gate 2 complete — PC veto check passed
4. ✓ Gate 3 complete — TD veto check passed
5. ✓ Scores aggregated with site-type weights
6. ✓ Grade assigned
7. ✓ `approval_probability` computed with disclaimer
8. ✓ `top_fixes` list generated (≥ 5 items)
9. ✓ `next_skills` array populated with context
10. ✓ JSON + Markdown report emitted
