# SEO Content Benchmark (SCB) v2.0

> SCB v2.0 is the offensive counterpart to ARB. ARB answers compliance and monetization eligibility. SCB answers ranking competitiveness and AI citability.

> 6 pillars, 106 criteria total (Core 80 + Extension 26).

---

## How to Read This Document

| Depth | Sections | You Will Learn |
|-------|----------|----------------|
| Skim | Parts 1-2 | What SCB v2.0 is and all criteria at a glance |
| Apply | Part 3 | How to score with 0-5 scale, veto gates, and profile weights |
| Operate | Part 4 | Workflow for manual and AI-agent assessment |
| Calibrate | scb-rubric-guidelines.md | 0/3/5 anchor rubric and examples |
| Customize | scb-profiles.md | 8 content-type profiles and extension mapping |

---

# Part 1: Framework Overview

## 1) SCB Positioning

SCB is for ranking and citation outcomes, not monetization policy outcomes.

| System | Primary Goal | Typical Outcome |
|--------|--------------|-----------------|
| ARB | Compliance and monetization readiness | Pass/fail risk reduction |
| SCB | Organic ranking and GEO performance | Traffic and citation uplift |

## 2) Evaluation Scope

SCB is page-first but includes essential site-level context signals.

- Page-level: content quality, E-E-A-T evidence, intent alignment, UX, AI extractability
- Site-level: topical cluster integrity, thin-content ratio, archive hygiene

## 3) YMYL Mode

When `ymyl: true`:

- `EA08` becomes a veto item (expert review required)
- Accuracy/citation thresholds are stricter
- Minimum pass threshold is raised from 60 to 70

## 4) Stage Tags

| Tag | Meaning |
|-----|---------|
| Pre | Required before publish |
| Active | Required after publish for maintenance |
| Both | Required in both phases |

## 5) Pillar Architecture

| Code | Pillar | Core | Ext | Total |
|------|--------|:----:|:---:|:-----:|
| IQ | Information Quality & Gain | 14 | 4 | 18 |
| EA | E-E-A-T & Authority | 16 | 4 | 20 |
| IA | Intent & Semantic Precision | 14 | 4 | 18 |
| FC | Freshness & Content Architecture | 14 | 4 | 18 |
| UX | User Experience & Behavior Signals | 12 | 4 | 16 |
| GE | Generative Engine Readiness | 10 | 6 | 16 |
| | Total | 80 | 26 | 106 |

## 6) Core Set and Extension Set

| Pillar | Core IDs | Ext IDs |
|--------|----------|---------|
| IQ | IQ01-IQ14 | IQ15-IQ18 |
| EA | EA01-EA16 | EA17-EA20 |
| IA | IA01-IA14 | IA15-IA18 |
| FC | FC01-FC14 | FC15-FC18 |
| UX | UX01-UX12 | UX13-UX16 |
| GE | GE01-GE10 | GE11-GE16 |

## 7) MECE Boundaries

| If issue is about... | Pillar |
|----------------------|--------|
| Knowledge depth, originality, info gain, anti-filler | IQ |
| Experience, credentials, authority, trust | EA |
| Query intent, SERP fit, semantics, entities | IA |
| Freshness, update discipline, cluster architecture | FC |
| Readability, scanability, dwell/long-click support | UX |
| AI extractability, schema completeness, citation structure | GE |

---

# Part 2: Complete 106-Item Checklist

One-line operational standard for each item. Detailed 0/3/5 anchors are in scb-rubric-guidelines.md.

## IQ - Information Quality & Gain (18)

| ID | Check Item | Stage | Standard |
|----|-----------|-------|----------|
| IQ01 | Query Completeness | Both | Fully resolves primary query and likely follow-ups |
| IQ02 | Use Case Coverage | Both | Covers practical scenarios and edge cases |
| IQ03 | Prerequisite Context | Both | Provides or links required background knowledge |
| IQ04 | Competitive Depth | Both | Goes deeper than top 5 SERP peers |
| IQ05 | Information Gain | Both | Adds new knowledge beyond existing ranking pages |
| IQ06 | First-Party Data | Both | Includes proprietary test/survey/usage data |
| IQ07 | Unique Perspective | Both | Offers non-obvious angle or synthesis |
| IQ08 | AI-Irreproducible Insight | Both | Contains human experiential insight not generic-AI reproducible |
| IQ09 | HCS Alignment | Both | Passes people-first helpful-content checks |
| IQ10 | People-First Writing | Both | Written to help users, not to stuff ranking signals |
| IQ11 | Title Honesty | Both | Title is specific and non-deceptive |
| IQ12 | Originality Gate (VETO) | Both | No plagiarism, no raw machine-translation, no zero-value AI filler |
| IQ13 | AI Value Threshold | Both | AI-assisted content has human-added value and verification |
| IQ14 | Minimum Value Floor | Both | No indexable stub/placeholder low-value page |
| IQ15 | Original Data Visualization | Both | Uses first-party charts/tables for new evidence |
| IQ16 | Expert Interview Evidence | Both | Includes exclusive expert input where relevant |
| IQ17 | Longitudinal Data | Both | Compares over time or across cohorts with method clarity |
| IQ18 | Cross-Domain Synthesis | Both | Combines disciplines to create additional insight |

## EA - E-E-A-T & Authority (20)

| ID | Check Item | Stage | Standard |
|----|-----------|-------|----------|
| EA01 | First-Person Narrative | Both | Demonstrates direct involvement where applicable |
| EA02 | Experiential Proof | Both | Includes screenshots/photos/test artifacts |
| EA03 | Problems Encountered | Both | Documents failures/limits honestly |
| EA04 | Engagement Depth | Both | States duration/scope of actual usage/testing |
| EA05 | Author Visibility | Pre | Author name/photo/bio visible on page |
| EA06 | Credential Verifiability | Both | Credentials are relevant and independently checkable |
| EA07 | Method Transparency | Both | Explains method, criteria, and reasoning path |
| EA08 | Expert Review Signal (YMYL VETO) | Both | YMYL content reviewed by qualified expert with visible attribution |
| EA09 | Third-Party Recognition | Both | Cited/recognized by authoritative external sources |
| EA10 | Author Entity Presence | Both | Author discoverable across reliable public entities |
| EA11 | Organization Entity Presence | Both | Publisher entity verifiable |
| EA12 | Entity Consistency | Both | Org identity consistent across major platforms |
| EA13 | Factual Accuracy & Citations | Both | Material claims are sourced and verifiable |
| EA14 | Disclosure Compliance | Both | Sponsored/affiliate/commercial relationships disclosed clearly |
| EA15 | Editorial Transparency | Both | Editorial/corrections standards are publicly available |
| EA16 | Non-Manipulative Framing | Both | Avoids fabricated urgency and deceptive persuasion |
| EA17 | Knowledge Graph Readiness | Both | Entity metadata supports KG inclusion |
| EA18 | External Authority Citations | Both | Academic/press/industry authority references present |
| EA19 | Award/Recognition Evidence | Both | Verifiable recognition included where claimed |
| EA20 | Correction History | Active | Corrections and updates are transparently logged |

## IA - Intent & Semantic Precision (18)

| ID | Check Item | Stage | Standard |
|----|-----------|-------|----------|
| IA01 | Intent Type Classification | Pre | Correctly classifies dominant query intent |
| IA02 | SERP Format Alignment (VETO) | Both | Content format matches dominant SERP intent pattern |
| IA03 | Micro-Moment Fit | Both | Serves user need immediately in first viewport |
| IA04 | PAA & Follow-Up Coverage | Both | Addresses common follow-up questions |
| IA05 | Cannibalization Control | Both | No internal intent-level conflict page |
| IA06 | Primary Keyword Placement | Pre | Present in title, H1, and early body naturally |
| IA07 | Semantic Breadth | Both | Covers topic vocabulary and related concepts naturally |
| IA08 | Entity Salience | Both | One dominant entity/topic is clear |
| IA09 | Entity Naming Precision | Both | Uses canonical entity names unambiguously |
| IA10 | No Keyword Stuffing (VETO) | Both | No manipulative repetition harming readability |
| IA11 | SERP Feature Targeting | Both | Structured to compete for snippet/PAA/rich features |
| IA12 | Mixed-Intent Handling | Both | Handles secondary intent where SERP requires |
| IA13 | Schema Fit for Intent | Both | Schema types match intent and pass validation |
| IA14 | Long-Tail Coverage | Both | Covers long-tail variants and sub-questions |
| IA15 | Voice Query Optimization | Both | Conversational Q-format and concise direct answers |
| IA16 | Snippet Block Design | Both | 40-70 word extractable answer blocks are present |
| IA17 | Multilingual Intent Consistency | Both | Intent and semantics aligned across languages |
| IA18 | Navigational Query Handling | Both | Brand/navigational queries resolve to canonical destination |

## FC - Freshness & Content Architecture (18)

| ID | Check Item | Stage | Standard |
|----|-----------|-------|----------|
| FC01 | Freshness Class Tagging | Pre | Classified as evergreen/periodic QDF/reactive QDF |
| FC02 | Publish Date Transparency | Both | Clear machine-readable published date |
| FC03 | Modified Date Integrity | Active | Last-updated reflects substantive revisions |
| FC04 | Source Currency | Both | Sources current enough for topic volatility |
| FC05 | Evergreen Language Discipline | Both | Avoids stale time-anchored wording in evergreen pages |
| FC06 | Topic Cluster Membership | Pre | Page belongs to explicit pillar-cluster map |
| FC07 | Pillar-Cluster Link Integrity | Both | Bidirectional links between pillar and cluster pages |
| FC08 | Internal Link Density | Both | Adequate contextual internal links to related pages |
| FC09 | Anchor Text Precision | Both | Anchors descriptive and semantically meaningful |
| FC10 | Content Gap Closure | Active | Closes missing subtopics competitors cover |
| FC11 | Historical Optimization Loop | Active | Declining pages enter scheduled update cycle |
| FC12 | Freshness Schema Fields | Both | datePublished and dateModified are correct |
| FC13 | QDF Response Capability | Active | Timely refresh mechanism on volatile topics |
| FC14 | Thin Content Ratio (VETO) | Both | Indexed thin-content proportion remains below 10% |
| FC15 | Visible Changelog | Both | Significant updates listed in a visible changelog |
| FC16 | Source Link Audit | Active | Citation links periodically checked and repaired |
| FC17 | Archive Hygiene Strategy | Active | Merge/noindex/redirect stale low-value assets |
| FC18 | Gap Audit Cadence | Active | Competitor gap audit run at least every 6 months |

## UX - User Experience & Behavior Signals (16)

| ID | Check Item | Stage | Standard |
|----|-----------|-------|----------|
| UX01 | Answer-First Structure | Both | Main answer/value visible immediately |
| UX02 | Pogo-Stick Prevention | Both | No long preamble before useful content |
| UX03 | Long-Click Optimization | Both | Page resolves intent deeply enough to prevent bounce-back |
| UX04 | TL;DR / Summary | Both | Long content offers early summary/takeaways |
| UX05 | Scannability | Both | Uses headings, bullets, tables, visual hierarchy |
| UX06 | Heading Hierarchy | Both | One H1 and logical H2-H6 structure |
| UX07 | Passage-Friendly Headings | Both | Headings are query-descriptive and extractable |
| UX08 | Section Autonomy | Both | Sections can stand alone for direct landing |
| UX09 | CTR Snippet Quality | Pre | Title/meta are clear, specific, benefit-oriented |
| UX10 | Mobile Readability | Both | Clean mobile rendering with usable touch targets |
| UX11 | Content-to-Noise Ratio | Both | Useful content dominates; intrusive UI minimized |
| UX12 | Engagement Pathing | Both | Includes next-step links/components |
| UX13 | TOC for Long Content | Both | Anchor-linked table of contents for long pages |
| UX14 | Reading Time Indicator | Both | Displays estimated read time where relevant |
| UX15 | Interactive Utility | Both | Embedded tools/interactions add real value |
| UX16 | Social Proof Integration | Both | Uses credible quotes/reviews/cases when relevant |

## GE - Generative Engine Readiness (16)

| ID | Check Item | Stage | Standard |
|----|-----------|-------|----------|
| GE01 | Definition-First Opening | Both | Starts with direct complete definition sentence |
| GE02 | Direct Answer Paragraph | Both | Includes concise standalone answer near top |
| GE03 | AEO Answer Format | Both | Q&A answers are self-contained and extraction-ready |
| GE04 | FAQ + Schema | Both | FAQ section with valid FAQPage markup |
| GE05 | Structured Data Tables | Both | Uses HTML tables for comparable data |
| GE06 | Inline Attribution | Both | Facts/stats have named in-line sources |
| GE07 | AI Attribution Readiness | Both | Clear author and org attribution on-page |
| GE08 | Citation Signal Density | Both | Multiple cite-ready fact blocks and named sources |
| GE09 | Entity Markup Coverage | Both | Person/Organization/Article entities marked up correctly |
| GE10 | AI Overview Structural Fit | Both | Uses structures favored by AI Overviews |
| GE11 | Featured Snippet Structure | Both | Query-aligned 40-70 word snippet blocks under relevant headings |
| GE12 | HowTo Schema | Both | Step-by-step pages include valid HowTo markup |
| GE13 | Cross-Platform Entity Consistency | Both | Entity descriptors consistent across web profiles |
| GE14 | Structured Data Completeness | Both | All applicable schema types implemented and valid |
| GE15 | GEO Performance Tracking | Active | Tracks AI mention/citation/overview trends |
| GE16 | Multilingual Schema Consistency | Both | Structured data remains consistent across locales |

---

# Part 3: Scoring System

## 0-5 Scale

| Score | Label | Meaning |
|-------|-------|---------|
| 5 | Exemplary | Best-practice implementation; clear competitive advantage |
| 4 | Good | Strong implementation with minor gaps |
| 3 | Adequate | Baseline publishable quality |
| 2 | Weak | Partial implementation below competitive threshold |
| 1 | Poor | Major deficiencies; substantial remediation required |
| 0 | Absent/Violation | Missing or disqualifying failure |

Formula:

Pillar Score = (sum of item scores / max possible) * 100

Total Score = sum(Pillar Score * Pillar Weight)

Score modes:

- Core 80
- Core 80 + Profile
- Full 106

## Profile Weights

| Pillar | Long-form | News | Review | How-to | YMYL | Tool | Comparison | UGC |
|--------|:---------:|:----:|:------:|:------:|:----:|:----:|:----------:|:---:|
| IQ | 20% | 15% | 20% | 15% | 20% | 15% | 15% | 25% |
| EA | 20% | 15% | 25% | 15% | 30% | 20% | 25% | 30% |
| IA | 20% | 20% | 15% | 25% | 15% | 20% | 20% | 15% |
| FC | 15% | 25% | 15% | 15% | 15% | 10% | 15% | 10% |
| UX | 15% | 15% | 15% | 20% | 10% | 20% | 15% | 10% |
| GE | 10% | 10% | 10% | 10% | 10% | 15% | 10% | 10% |

## Grade Scale

| Score | Grade |
|-------|-------|
| 90-100 | Competitive Ready |
| 75-89 | Near Ready |
| 60-74 | Needs Work |
| 40-59 | Major Gaps |
| 0-39 | Not Ready |

YMYL mode minimum pass threshold: 70.

## Veto Gates

| Gate | Trigger |
|------|---------|
| IQ12 | Plagiarism/raw machine translation/zero-value AI filler |
| IA02 | Fundamental SERP intent mismatch |
| IA10 | Manipulative keyword stuffing |
| FC14 | Thin-content ratio above threshold |
| EA08 (YMYL) | No qualified expert review or material factual error |

---

# Part 4: Workflow

1. Gate 1: Intent and veto pre-check (IA focus)
2. Gate 2: Quality and architecture (IQ and FC)
3. Gate 3: Trust, UX, GEO (EA, UX, GE)
4. Gate 4: Weighted scoring and remediation report

For AI-agent workflows, use:

- this file for item definitions
- scb-profiles.md for profile weights and extension mapping
- scb-rubric-guidelines.md for 0/3/5 anchor calibration

---

# Part 5: Design Principles

1. Information gain is a first-class ranking differentiator.
2. E-E-A-T is evaluated as four independent axes, not one blended signal.
3. Page quality and site architecture must be assessed together.
4. GEO is a parallel optimization track, not a substitute for core quality.
5. SCB and ARB should run as a dual operating system: ARB first (defense), SCB second (offense).
