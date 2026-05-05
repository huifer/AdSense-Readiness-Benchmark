# Google Ads Review Lifecycle Skills

Complete skill suite for navigating Google AdSense review process across all lifecycle phases: pre-approval, active monitoring, and rejection recovery.

This skill map follows the ARB mixed model:
- Always start from the fixed `Core 79` review set.
- Add the primary site type's extension profile when running `Core 79 + Profile` mode.
- Add any conditional trigger items defined in [../ARB-benchmark.md](../ARB-benchmark.md) when the site's risk surface requires them.
- Fall back to full 105-item coverage when the site spans multiple business models or the audit brief requires full scope.
- Add benchmark overlays when stakeholders need approval probability, competitive context, regional compliance, or multi-network monetization planning.

## Quick Navigation

### 🎯 Default Entry Point
**[arb-full-audit](./arb-full-audit/)** — Start here for the unified 4-gate audit orchestrator

Recommended fallback entry:
**[ads-readiness-assessment](./ads-readiness-assessment/)** — Use when you want triage only instead of the full orchestrated audit

### 📋 By Phase

#### Pre-flight Phase (Before Submission)
1. [arb-full-audit](./arb-full-audit/) - Unified 4-gate full audit
2. [ads-readiness-assessment](./ads-readiness-assessment/) - Full diagnostic
3. [content-audit](./content-audit/) - Content quality check
4. [technical-audit](./technical-audit/) - Technical health scan
5. [ux-compliance-audit](./ux-compliance-audit/) - UX compliance verification
6. [policy-risk-scanner](./policy-risk-scanner/) - Policy violation detection
7. [content-improvement-blueprint](./content-improvement-blueprint/) - Content fixes
8. [technical-remediation-guide](./technical-remediation-guide/) - Technical fixes
9. [ux-optimization-roadmap](./ux-optimization-roadmap/) - UX improvements
10. [policy-remediation-plan](./policy-remediation-plan/) - Policy compliance plan
11. [trust-credibility-strategy](./trust-credibility-strategy/) - Trust building strategy
12. [resubmission-readiness-check](./resubmission-readiness-check/) - Final verification

#### Scale, Benchmark, and Monetization Phase
1. [ai-content-compliance](./ai-content-compliance/) - AI-generated content risk assessment
2. [multi-network-readiness](./multi-network-readiness/) - Ad network readiness comparison
3. [revenue-potential-estimator](./revenue-potential-estimator/) - Revenue and RPM upside modeling
4. [geo-localization-compliance](./geo-localization-compliance/) - Region-specific compliance and consent review
5. [competitive-benchmark](./competitive-benchmark/) - Industry baseline and competitor gap analysis
6. [agency-batch-auditor](./agency-batch-auditor/) - Multi-site agency workflow and ranking
7. [scb-profile-router](./scb-profile-router/) - SCB content profile routing, weight resolution, and extension trigger mapping
8. [scb-execution-planner](./scb-execution-planner/) - SCB remediation sequencing, batching, and recheck planning

#### Active Phase (After Approval)
1. [active-compliance-monitor](./active-compliance-monitor/) - Automated monitoring setup
2. [health-check-automation](./health-check-automation/) - Periodic health checks
3. [alert-rules-setup](./alert-rules-setup/) - Alert configuration

#### Recovery Phase (After Rejection)
1. [rejection-root-cause-analysis](./rejection-root-cause-analysis/) - Analyze rejection
2. [recovery-action-plan](./recovery-action-plan/) - Create action plan
3. [resubmission-readiness-check](./resubmission-readiness-check/) - Verify fixes
4. [appeal-strategy-builder](./appeal-strategy-builder/) - Build appeal (optional)

#### Cross-Phase (All Phases)
1. [affiliate-link-compliance](./affiliate-link-compliance/) - Affiliate disclosure check
2. [copyright-ip-check](./copyright-ip-check/) - Copyright & IP verification
3. [seo-spam-detection](./seo-spam-detection/) - SEO spam detection

---

## 28 Skills Overview

### Layer 1: Orchestration (1 skill)

| Skill | Purpose | Input | Output |
|-------|---------|-------|--------|
| [arb-full-audit](./arb-full-audit/) | Unified 4-gate audit orchestration | URL + site type + score mode | Consolidated Markdown + JSON report |

### Layer 2: Diagnostic & Assessment (5 skills)

| Skill | Purpose | Input | Output |
|-------|---------|-------|--------|
| [ads-readiness-assessment](./ads-readiness-assessment/) | Comprehensive site diagnosis | Website URL or project path | Interactive survey + JSON report |
| [content-audit](./content-audit/) | Content Integrity check | Website or source files | Markdown checklist + quality score |
| [technical-audit](./technical-audit/) | Technical Health scan | Website URL | Structured fixes + priority order |
| [ux-compliance-audit](./ux-compliance-audit/) | UX compliance verify | Website or design files | Visual survey + WCAG report |
| [policy-risk-scanner](./policy-risk-scanner/) | Policy violation detect | Website content | Risk classification + warnings |

### Layer 3: Improvement & Remediation Guides (5 skills)

| Skill | Purpose | Input | Output |
|-------|---------|-------|--------|
| [content-improvement-blueprint](./content-improvement-blueprint/) | Content fixing guide | Violations from content-audit | Detailed guide + examples |
| [technical-remediation-guide](./technical-remediation-guide/) | Technical fixing guide | Issues from technical-audit | Code snippets + configs |
| [ux-optimization-roadmap](./ux-optimization-roadmap/) | UX improvement plan | Issues from ux-compliance-audit | Phased roadmap + specs |
| [policy-remediation-plan](./policy-remediation-plan/) | Policy compliance plan | Risks from policy-risk-scanner | Action plan + templates |
| [trust-credibility-strategy](./trust-credibility-strategy/) | Trust building strategy | Trust & disclosure evaluation | Multi-phase strategy |

### Layer 4: Monitoring & Maintenance (3 skills)

| Skill | Purpose | Output |
|-------|---------|--------|
| [active-compliance-monitor](./active-compliance-monitor/) | Setup monitoring rules | Configuration guide + alert rules |
| [health-check-automation](./health-check-automation/) | Generate check scripts | Node.js / Python / Bash scripts |
| [alert-rules-setup](./alert-rules-setup/) | Configure alerts | Integration guide + rule configs |

### Layer 5: Rejection Recovery (4 skills)

| Skill | Purpose | Input | Output |
|-------|---------|-------|--------|
| [rejection-root-cause-analysis](./rejection-root-cause-analysis/) | Analyze rejection | Google rejection notice | Root cause analysis + mapping |
| [recovery-action-plan](./recovery-action-plan/) | Create recovery plan | Root cause analysis | Week-by-week action plan |
| [resubmission-readiness-check](./resubmission-readiness-check/) | Verify before resubmit | Completed fixes | Pre-submission checklist |
| [appeal-strategy-builder](./appeal-strategy-builder/) | Build appeal strategy | Disputed rejection | Appeal letter + evidence guide |

### Layer 6: Cross-Phase Checks (3 skills)

| Skill | Purpose | Applies To |
|-------|---------|-----------|
| [affiliate-link-compliance](./affiliate-link-compliance/) | Affiliate disclosure check | Pre-flight / Active / Recovery |
| [copyright-ip-check](./copyright-ip-check/) | Copyright & IP review | Pre-flight / Active / Recovery |
| [seo-spam-detection](./seo-spam-detection/) | SEO spam detection | Pre-flight / Active / Recovery |

### Layer 7: Scale, Benchmark, and Monetization (8 skills)

| Skill | Purpose | Applies To |
|-------|---------|-----------|
| [ai-content-compliance](./ai-content-compliance/) | AI-assisted content quality and editorial control review | Pre-flight / Active |
| [multi-network-readiness](./multi-network-readiness/) | AdSense-to-premium-network gap analysis | Pre-flight / Growth planning |
| [revenue-potential-estimator](./revenue-potential-estimator/) | RPM upside and monetization scenario modeling | Planning / Prioritization |
| [geo-localization-compliance](./geo-localization-compliance/) | Regional privacy, consent, and disclosure review | Multi-market / Active |
| [competitive-benchmark](./competitive-benchmark/) | Industry baseline and competitor comparison | Planning / Prioritization |
| [agency-batch-auditor](./agency-batch-auditor/) | Multi-site batch auditing and white-label delivery | Agency / Portfolio |
| [scb-profile-router](./scb-profile-router/) | SCB profile detection, weighting merge, and extension trigger routing | Planning / Scoring setup |
| [scb-execution-planner](./scb-execution-planner/) | SCB score-to-remediation conversion with veto-first task batching | Planning / Remediation tracking |

---

## Workflow Diagrams

### Pre-flight to Approval

```
Start
  ↓
[arb-full-audit]
  ↓
(or use [ads-readiness-assessment] for triage-only mode)
  ↓
[ads-readiness-assessment]
  ├─→ [content-audit] ──→ [content-improvement-blueprint]
  ├─→ [technical-audit] ──→ [technical-remediation-guide]
  ├─→ [ux-compliance-audit] ──→ [ux-optimization-roadmap]
  ├─→ [policy-risk-scanner] ──→ [policy-remediation-plan]
  └─→ [trust-credibility-strategy]
       ↓ (all paths converge)
[resubmission-readiness-check]
  ├─→ [affiliate-link-compliance]
  ├─→ [copyright-ip-check]
  └─→ [seo-spam-detection]
  ↓
Submit to Google
  ↓
✓ Approved → [active-compliance-monitor] + [health-check-automation] + [alert-rules-setup]
```

### Recommended Score Modes

| Mode | Use When | Minimum Scope |
|------|----------|---------------|
| `Core 79` | Fast baseline triage or internal readiness check | Fixed core 79 items only |
| `Core 79 + Profile` | Standard audit for one primary site type | Core 79 + one site-type extension profile + triggered items |
| `Full 105` | Public-facing audits, mixed-model sites, or ambiguous briefs | All 105 benchmark items |

### Site-Type Routing

| Site Type | Start Here | Typical Extensions to Expect |
|-----------|------------|------------------------------|
| Blog / Content | [ads-readiness-assessment](./ads-readiness-assessment/) + [content-audit](./content-audit/) | Freshness, citations, multimedia, error-page, and editorial trust extensions |
| Tool / SaaS | [ads-readiness-assessment](./ads-readiness-assessment/) + [technical-audit](./technical-audit/) | Reliability, performance, error-handling, entity, and compliance-depth extensions |
| Affiliate | [ads-readiness-assessment](./ads-readiness-assessment/) + [affiliate-link-compliance](./affiliate-link-compliance/) | Disclosure, ad-code, outbound link, and trust-depth extensions |
| News / Aggregator | [ads-readiness-assessment](./ads-readiness-assessment/) + [content-audit](./content-audit/) + [seo-spam-detection](./seo-spam-detection/) | Freshness, pagination, citation, and link-quality extensions |
| E-commerce | [ads-readiness-assessment](./ads-readiness-assessment/) + [technical-audit](./technical-audit/) + [trust-credibility-strategy](./trust-credibility-strategy/) | Refund, shipping, entity, monetization, and operational reliability extensions |
| Forum / Community | [ads-readiness-assessment](./ads-readiness-assessment/) + [seo-spam-detection](./seo-spam-detection/) | UGC-link, moderation, pagination, and uptime extensions |

### Rejection to Resubmission

```
Rejection Received
  ↓
[rejection-root-cause-analysis]
  ↓
[recovery-action-plan]
  ├─→ [content-improvement-blueprint]
  ├─→ [technical-remediation-guide]
  ├─→ [policy-remediation-plan]
  └─→ ... (iterate on improvements)
  ↓
[resubmission-readiness-check]
  ↓
(Optional) [appeal-strategy-builder]
  ↓
Resubmit or Appeal
```

---

## Getting Started

### For Website Owners (Self-assessment)
1. Start: [arb-full-audit](./arb-full-audit/)
2. Follow improvement guides for each area
3. Use [resubmission-readiness-check](./resubmission-readiness-check/) before submitting
4. After approval, run [health-check-automation](./health-check-automation/) regularly

### For Consultants/Agencies (Client Assessment)
1. Run [agency-batch-auditor](./agency-batch-auditor/) for portfolios or [arb-full-audit](./arb-full-audit/) for single-client audits
2. Export detailed diagnostic report
3. Use improvement guides to build client roadmap
4. Track progress with [active-compliance-monitor](./active-compliance-monitor/) (post-approval)

### For Rejection Recovery
1. Start: [rejection-root-cause-analysis](./rejection-root-cause-analysis/)
2. Follow: [recovery-action-plan](./recovery-action-plan/)
3. Verify: [resubmission-readiness-check](./resubmission-readiness-check/)
4. (Optional) Appeal: [appeal-strategy-builder](./appeal-strategy-builder/)

---

## Supported Check Modes

Each skill supports multiple check modes:

- **URL Mode**: Input website URL → automatic crawling and analysis
- **Source Mode**: Analyze local project source code
- **Manual Mode**: Interactive guidance for manual verification

---

## Check Modes by Skill

| Skill | URL Mode | Source Mode | Manual Mode |
|-------|----------|-------------|------------|
| ads-readiness-assessment | ✓ | ✓ | ✓ |
| content-audit | ✓ | ✓ | ✓ |
| technical-audit | ✓ | ✓ | ✓ |
| ux-compliance-audit | ✓ | ✓ | ✓ |
| policy-risk-scanner | ✓ | ✓ | ✓ |
| affiliate-link-compliance | ✓ | ✓ | ✓ |
| copyright-ip-check | ✓ | ✓ | ✓ |
| seo-spam-detection | ✓ | ✓ | ✓ |
| health-check-automation | ✓ | ✓ | - |
| active-compliance-monitor | - | - | ✓ |
| arb-full-audit | ✓ | ✓ | ✓ |
| ai-content-compliance | ✓ | ✓ | ✓ |
| multi-network-readiness | ✓ | ✓ | ✓ |
| revenue-potential-estimator | ✓ | ✓ | ✓ |
| geo-localization-compliance | ✓ | ✓ | ✓ |
| competitive-benchmark | ✓ | ✓ | ✓ |
| agency-batch-auditor | ✓ | ✓ | ✓ |
| scb-profile-router | ✓ | ✓ | ✓ |
| scb-execution-planner | ✓ | ✓ | ✓ |
| (Others) | - | - | ✓ |

---

## Output Formats

Each skill produces outputs in multiple formats:

- **Markdown**: Human-readable reports and guides
- **JSON**: Structured data for integration and processing
- **Scripts**: Automated checking and remediation code (JS, Python, Bash)
- **Templates**: Ready-to-use files (policies, configs, plans)
- **Checklists**: Interactive surveys and verification checklists

When a skill contributes to scoring, outputs should declare the score mode or at least identify whether the result is intended for `Core 79`, `Core 79 + Profile`, or `Full 105` aggregation.

---

## Key Features

### Strong Coupling
Skills automatically invoke related skills to create complete workflows:
- Diagnostic → Improvement guide → Verification
- Rejection analysis → Action plan → Readiness check

### Multi-Role Support
- **Website Owners**: Self-serve diagnostics and improvement guides
- **Developers**: Technical remediation and automation scripts
- **Content Teams**: Content improvement and originality checking
- **Compliance Officers**: Policy and risk monitoring
- **Consultants**: Full diagnostic reports and recovery strategies

### Comprehensive Coverage
- All ARB 105 evaluation criteria mapped to skills
- Core 79 baseline path plus site-type and trigger-based extension coverage
- Complete lifecycle from pre-submission to active compliance
- Full rejection recovery workflow including appeals

---

## Related Resources

- **ARB Framework**: See [../ARB-benchmark.md](../ARB-benchmark.md) for evaluation criteria
- **Scoring Modes**: See [../ARB-benchmark.md](../ARB-benchmark.md) for core 79, site-type profiles, and conditional triggers
- **Agents**: See [../AGENTS.md](../AGENTS.md) for AI-driven assistants
- **Google AdSense Policies**: [Google Publisher Policies](https://support.google.com/adsense/answer/10502938)

---

## Contributing

Each skill follows standard structure:
- `SKILL.md` - Main skill definition and workflow
- `{name}-prompt.md` - AI agent instructions (where applicable)
- `{name}-template.md` - Output templates
- `{name}-checks.{js|py|sh}` - Automated checking scripts

