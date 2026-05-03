# ARB Agent Guidelines

This guide defines quality requirements for contributors and AI agents working on ARB skills, scripts, and benchmark logic.

## Mission

Protect audit credibility.

ARB outputs should be reproducible, evidence-based, and policy-aligned. Low-confidence guesses, fabricated findings, or opaque scoring logic are treated as defects.

## Non-Negotiable Rules

1. Do not invent evidence.
2. Do not infer a passing result without data.
3. Do not silently change scoring rules or item mappings.
4. Do not suppress veto signals because overall score looks high.
5. Do not return success if required artifacts are missing.
6. Do not mix `Core 79`, `Core 79 + Profile`, and `Full 105` scoring modes without naming the chosen mode explicitly.

## Required Validation Before Final Output

For any checker, skill, or future orchestrator change:

1. Confirm item coverage has not regressed.
2. Confirm the declared score mode (`Core 79`, `Core 79 + Profile`, or `Full 105`) matches the actual evaluated item set.
3. Confirm any site-type extension profile and conditional trigger items are documented when used.
2. Confirm output schema remains backward compatible, or document breaking changes.
3. Run at least one known-safe URL and one intentionally risky URL.
4. Verify veto precedence is preserved in final report generation.
5. Verify conflict handling remains explicit for dual-scored items (notably PC10).

## Required Output Characteristics

Every checker output should include:

- `status` and `score` for each covered item
- A short evidence-backed `finding`
- Any `veto_triggered` state when applicable
- The declared `score_mode` and the evaluated item set or profile name
- Sufficient metadata to trace script behavior (URL, timestamp, notable flags)
- `approval_probability` when producing a consolidated or decision-grade audit report, labeled as a statistical estimate rather than an official Google signal

## Change Boundaries

- `ARB-benchmark.md` is the policy contract. If definitions change there, checker logic and docs must be updated together.
- The fixed core 79 set, site-type extension profiles, and conditional trigger rules are part of that policy contract.
- If you add a new signal, map it to an explicit ARB item.
- If one signal may affect multiple items, explain that relationship in the skill doc and output notes.
- `skills/README.md` and `skills/arb-full-audit/SKILL.md` are the current execution contract for repository users.

## Routing Expectations

Use these routes consistently when deciding which skill to invoke first or next:

- Default entry: `arb-full-audit`
- Triage-only path: `ads-readiness-assessment`
- AI-assisted or scaled content concerns: `ai-content-compliance`
- Multi-network monetization planning: `multi-network-readiness`
- Revenue prioritization or ROI framing: `revenue-potential-estimator`
- Multi-country, multilingual, or privacy-law complexity: `geo-localization-compliance`
- Market context or category positioning: `competitive-benchmark`
- Multi-site portfolio, consultant, or agency workflows: `agency-batch-auditor`

If a request touches multiple of the above, prefer `arb-full-audit` first and then route into the specialized overlay skills.

## Confidence and Escalation

Use these patterns consistently:

- If evidence is ambiguous, prefer `Partial` with a manual-review note over speculative `Fail`.
- If extraction failed (timeout, JS rendering limits), return explicit uncertainty and avoid false precision.
- If policy risk appears severe (PC01-PC09), escalate clearly even when confidence is moderate.

## Script and Skill Design Expectations

- Keep scripts deterministic and side-effect minimal.
- Keep skill instructions aligned with actual script interfaces.
- Keep JSON structures stable and easy to aggregate.
- Prefer additive schema evolution with clear defaults.
- If a skill claims to cover only the baseline path, say whether it is intended for `Core 79` only or also contributes extension items.

## Review Checklist for PRs/Commits

1. Is the problem statement concrete and reproducible?
2. Are item mappings and scoring rules unchanged or explicitly documented?
3. Is the score mode explicit, and does it match the benchmark profile/trigger rules?
4. Are edge cases and failure modes handled explicitly?
5. Are veto and conflict paths tested?
6. Are docs updated where behavior changed?

## Definition of Done

A change is done only when:

1. Skill docs, scripts, and benchmark expectations are consistent.
2. Outputs are evidence-rich and machine-consumable.
3. Veto precedence and weighted scoring both behave correctly.
4. The chosen score mode and any profile/trigger additions are visible in the result path.
5. A human reviewer can reproduce the result path from artifacts.
