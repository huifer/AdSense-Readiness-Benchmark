---
name: ai-content-compliance
description: "Assess AI-generated content risk, value-add depth, disclosure practices, and human editorial oversight for AdSense and broader publisher monetization readiness."
---

# AI Content Compliance

Evaluate whether AI-assisted or AI-generated content creates monetization risk under AdSense-style helpful content, originality, disclosure, and E-E-A-T expectations.

## Quick Start

**Input**: Website URL, content samples, editorial workflow notes  
**Output**: AI content risk report + pass/partial/fail matrix + remediation plan  
**Time**: 20-45 minutes

## When To Use

Use this skill when:
- A site publishes AI-assisted or AI-generated content at scale
- Content quality looks templated, thin, repetitive, or low-value
- Editorial teams need a defensible policy for AI use
- You want to reduce rejection risk tied to low-originality or unhelpful content

## Scope

This skill overlays ARB items with deeper AI-specific review, especially:
- CI02, CI03, CI08, CI10, CI15, CI18
- TD11, TD12, TD20 when authorship and disclosure are weak
- SI01, SI02 when AI output creates keyword stuffing or semantic redundancy

## Review Dimensions

1. **Original value-add**
- Does the content go beyond summarization or paraphrase?
- Is there first-hand experience, testing, examples, or synthesis?

2. **Human editorial control**
- Is there evidence of human review, editing, fact-checking, and sign-off?
- Are expert-sensitive pages reviewed by qualified editors?

3. **Repetition risk**
- Are many pages structurally identical with only keyword swaps?
- Are intros, FAQs, and conclusions repeated across clusters?

4. **Disclosure quality**
- If AI materially contributes, is the workflow internally documented?
- If user trust would be affected, is public disclosure appropriate?

5. **Accuracy and citation depth**
- Are factual claims sourced?
- Do citations point to primary or authoritative sources?

6. **Brand and trust signals**
- Is authorship clear?
- Do editorial standards and update policies exist?

## Output Contract

Return:
- `ai_content_risk`: low / medium / high / critical
- `editorial_maturity`: low / medium / high
- `ai_usage_pattern`: assisted / hybrid / majority-generated / unknown
- `approval_impact`: negligible / moderate / material / severe
- `mapped_items`: ARB item IDs affected
- `priority_actions`: top remediation list

## Rating Guide

### Pass
- AI is clearly used as drafting support, not substitute for value
- Content shows strong human editing, expert input, and factual grounding
- No pattern of large-scale templated thin content

### Partial
- Some pages have value, but quality is inconsistent
- Human oversight exists but is weakly documented
- Repetition or shallow synthesis appears in some clusters

### Fail
- Large-scale low-value AI content with minimal differentiation
- Weak or no human oversight
- Repeated structures, unsupported claims, or obvious content spinning

## Recommended Remediation

1. Reduce low-value page count before expanding output volume
2. Add editor review workflow with named approvers
3. Require original examples, screenshots, testing notes, or data per page
4. Improve citations toward primary sources
5. Consolidate overlapping pages created from keyword variants
6. Add editorial standards page if trust is weak

## Routing

- If risk is `high` or `critical` → `content-improvement-blueprint`
- If trust signals are weak → `trust-credibility-strategy`
- If the site uses AI across many locales → `geo-localization-compliance`
- If benchmark comparison is needed → `competitive-benchmark`
