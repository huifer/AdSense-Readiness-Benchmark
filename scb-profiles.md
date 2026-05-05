# SCB v2.0 — Content-Type Profiles & Extension Item Specifications

> This file defines the 8 content-type profiles for the SEO Content Benchmark (SCB v2.0).
> Each profile specifies: pillar weight adjustments, recommended extension items, conditional triggers, and profile-specific scoring notes.
> Reference this file when selecting a profile in Part 1 of `seo-content-benchmark.md`.

---

## How to Use This File

1. **Select the primary profile** that matches your content piece from the 8 types below.
2. **Apply the pillar weights** from the selected profile's weight table.
3. **Add the recommended extension items** to the Core 80 set.
4. **Check conditional triggers** — add any additionally triggered items.
5. **Note profile-specific veto conditions** before scoring.

If a content piece spans multiple profiles (e.g., a long-form guide that is also YMYL), use the **union of both profiles' extension items** and the **stricter of the two weight configurations** for each pillar.

---

## Master Weight Reference

| Pillar | Long-form | News | Review | How-to | YMYL | Tool | Comparison | UGC |
|--------|:---------:|:----:|:------:|:------:|:----:|:----:|:----------:|:---:|
| **IQ** | 20% | 15% | 20% | 15% | 20% | 15% | 15% | 25% |
| **EA** | 20% | 15% | 25% | 15% | 30% | 20% | 25% | 30% |
| **IA** | 20% | 20% | 15% | 25% | 15% | 20% | 20% | 15% |
| **FC** | 15% | 25% | 15% | 15% | 15% | 10% | 15% | 10% |
| **UX** | 15% | 15% | 15% | 20% | 10% | 20% | 15% | 10% |
| **GE** | 10% | 10% | 10% | 10% | 10% | 15% | 10% | 10% |

---

## Profile 1: Long-form Guide

**Use when**: Content is a comprehensive educational guide, deep-dive explainer, whitepaper, or resource article targeting informational queries with high competition.

**Typical length**: 2,000–8,000+ words.

**Examples**: "The Complete Guide to Email Marketing," "What is Machine Learning?", "How to Start a SaaS Company."

### Pillar Weights

| IQ | EA | IA | FC | UX | GE |
|:--:|:--:|:--:|:--:|:--:|:--:|
| 20% | 20% | 20% | 15% | 15% | 10% |

### Recommended Extension Items

| Item | Reason |
|------|--------|
| IQ15 | Long-form guides benefit most from original data visualizations as differentiation |
| IQ18 | Cross-domain synthesis is a key competitive edge for comprehensive topics |
| FC15 | Long-form evergreen content requires visible update changelogs for trust and freshness signaling |
| FC17 | Archive strategy is critical for sites with large guide libraries |
| UX13 | Table of contents is mandatory for navigation in long-form content |
| UX14 | Reading time estimate is standard UX for long-form content |
| GE11 | Featured snippet targeting is highest-value for informational long-form content |

### Scoring Notes

- IQ04 (Competitive Depth Advantage) carries disproportionate impact for long-form guides — this is the primary differentiator vs. competing guides.
- FC06–FC07 (Topic Cluster Membership and Pillar Linkage) are near-mandatory; a long-form guide without a cluster structure is an orphaned asset.
- UX04 (TL;DR / Summary) is effectively required for content over 2,000 words.

---

## Profile 2: News & Trending

**Use when**: Content covers time-sensitive topics, breaking news, current events, or rapidly evolving developments where freshness is a primary ranking factor.

**Typical length**: 400–1,500 words.

**Examples**: "Google Announces Core Update," "Fed Raises Interest Rates," "New AI Model Benchmark Results."

### Pillar Weights

| IQ | EA | IA | FC | UX | GE |
|:--:|:--:|:--:|:--:|:--:|:--:|
| 15% | 15% | 20% | 25% | 15% | 10% |

### Recommended Extension Items

| Item | Reason |
|------|--------|
| FC15 | News content should log substantive updates prominently |
| FC16 | Source link rot is a major freshness risk for news content |
| IQ16 | Expert quotes or statements are primary information gain drivers for news |
| UX13 | Even shorter news pieces benefit from anchor navigation when covering multiple aspects |
| GE11 | News content frequently appears in AI Overviews when correctly structured |
| GE14 | Structured data completeness (NewsArticle schema) directly affects AI citation eligibility |

### Scoring Notes

- FC pillar is the dominant scoring dimension — FC01 (Freshness Classification), FC02 (Publication Date Transparency), and FC03 (Last Modified Date Integrity) must all score 4–5.
- QDF (Query Deserves Freshness) logic applies: if the query is trending, a fresh piece will temporarily outrank older high-authority pages. FC13 (QDF Response Capability) is critical.
- EA scoring is deliberately lower-weighted because news credibility at the organization level (EA11, EA12) is more important than individual author E-E-A-T for this format.
- IQ09 (HCS Self-Assessment Pass) requires that news content provides genuine original reporting — not just aggregation or rewriting of other sources.

---

## Profile 3: Product Review

**Use when**: Content evaluates a single product, service, or tool from a first-hand testing perspective. Includes single-product reviews, multi-product comparison reviews ("Best X" listicles with individual evaluations), and unboxing / hands-on assessments.

**Typical length**: 1,200–4,000 words.

**Examples**: "iPhone 16 Pro Review," "Best CRM Software for Small Business," "Jasper AI Review: 6 Months of Testing."

### Pillar Weights

| IQ | EA | IA | FC | UX | GE |
|:--:|:--:|:--:|:--:|:--:|:--:|
| 20% | 25% | 15% | 15% | 15% | 10% |

### Recommended Extension Items

| Item | Reason |
|------|--------|
| IQ15 | Original product photos, test screenshots, and data charts are primary IGS drivers |
| IQ16 | Expert quotes add authority for complex technical products |
| FC15 | Review accuracy must be logged when product features change |
| UX15 | Interactive scoring tools or comparison calculators significantly improve review UX |
| UX16 | Aggregated user ratings or community validation signals strengthen review credibility |
| GE11 | "Best [product type]" queries are high-value Featured Snippet targets |

### Scoring Notes

- **EA01–EA04 (Experience sub-group) are the most critical items in this profile.** A product review without first-hand testing evidence (EA02), documented problems encountered (EA03), and stated engagement duration (EA04) will consistently lose to reviews that provide these signals.
- EA14 (Disclosure Compliance) is effectively a veto condition for this profile — affiliate links without disclosure violate both FTC regulations and ARB PC10. Score 0 triggers the veto flag.
- IQ06 (First-Party Original Data) receives elevated importance: original test data, benchmark numbers, or before/after measurements are the strongest differentiators for review content.
- FC04 (Source Currency) applies to product specifications and pricing — outdated spec tables are a major trust and freshness risk.

---

## Profile 4: How-to & Tutorial

**Use when**: Content provides step-by-step instructional guidance for completing a task, learning a skill, or solving a specific problem.

**Typical length**: 800–3,000 words.

**Examples**: "How to Set Up Google Analytics 4," "How to Write a Cold Email," "How to Build a React App from Scratch."

### Pillar Weights

| IQ | EA | IA | FC | UX | GE |
|:--:|:--:|:--:|:--:|:--:|:--:|
| 15% | 15% | 25% | 15% | 20% | 10% |

### Recommended Extension Items

| Item | Reason |
|------|--------|
| IA15 | Voice search queries are heavily how-to phrased ("how do I…") |
| IA16 | Featured Snippet capture is highly achievable for step-based how-to content |
| UX13 | Table of contents is critical for multi-step tutorials |
| UX14 | Reading time helps users gauge commitment before starting |
| GE12 | HowTo Schema implementation is directly applicable and impactful |
| GE11 | How-to content is a primary source for AI Overviews citations |

### Scoring Notes

- IA02 (SERP Format Alignment) is especially critical: if the SERP shows video-heavy or step-by-step results, text-only content without numbered steps and visuals will consistently underperform.
- UX07 (Passage Ranking: Heading Quality) and UX08 (Section Autonomy) are high-value for how-to content — each step should be a self-contained passage Google can independently surface.
- GE12 (HowTo Schema) should be treated as near-mandatory for this profile; it is the most directly applicable extension item.
- IQ02 (Use Case & Edge Case Coverage) matters significantly: tutorials that cover common failure modes and alternative paths score higher than linear step-only guides.

---

## Profile 5: YMYL Content

**Use when**: Content falls into a high-stakes category where inaccurate information could cause real-world harm. Automatically triggers YMYL mode in the scoring system.

**YMYL Categories**: Medical / health, financial decisions, legal guidance, safety information, major life decisions, civic / political content, child-related advice.

**Typical length**: 1,500–6,000+ words.

**Examples**: "Symptoms of Type 2 Diabetes," "How to Write a Will," "Best Index Funds for Retirement."

### Pillar Weights

| IQ | EA | IA | FC | UX | GE |
|:--:|:--:|:--:|:--:|:--:|:--:|
| 20% | 30% | 15% | 15% | 10% | 10% |

### YMYL Mode Activations

When this profile is selected, the following additional rules apply:

| Item | Activation |
|------|-----------|
| EA08 | Becomes a **veto item** — content cannot proceed without credentialed expert review |
| IQ13 | AI-generated content requires expert review of every factual claim before publishing |
| FC04 | Source currency threshold tightens: primary sources must be within 1 year for clinical/regulatory topics |
| Grade threshold | Minimum passing grade elevated from 60 to **70** |

### Recommended Extension Items

| Item | Reason |
|------|--------|
| EA17 | Wikipedia entity presence significantly boosts YMYL trust signals |
| EA18 | Academic or press citation is a top-tier authority signal for medical/financial content |
| EA20 | Corrections history is especially important for YMYL accuracy accountability |
| IQ16 | Expert interview quotes are a primary differentiation mechanism for YMYL content |
| FC15 | YMYL content update changelogs are required to demonstrate regulatory / clinical tracking |
| FC16 | Source link audits are critical — dead links to medical/legal authorities are trust failures |
| GE14 | Structured data for MedicalCondition, FAQPage, Article with credentialing markup increases AI citation eligibility |

### Scoring Notes

- EA sub-group scoring thresholds are elevated across all four dimensions for YMYL content. Scores that would be Adequate (3) in other profiles are treated as Weak (2) in this context.
- IQ13 (AI-Assisted Content Value Threshold) requires that all AI-generated factual claims are verified against primary sources by a qualified reviewer — not just a copyeditor.
- Risk disclaimers and "consult a professional" language are required but must not substitute for content quality. Their presence contributes to EA13 (Trust) but does not offset low EA06 or EA08 scores.

---

## Profile 6: Tool & Landing Page

**Use when**: Content is a functional tool page, SaaS product landing page, service page, or calculator that serves users through interaction rather than passive reading.

**Typical length**: 400–2,000 words of text content alongside the tool/product interface.

**Examples**: "Free Word Count Tool," "HubSpot CRM — Features and Pricing," "ROI Calculator for SEO Investment."

### Pillar Weights

| IQ | EA | IA | FC | UX | GE |
|:--:|:--:|:--:|:--:|:--:|:--:|
| 15% | 20% | 20% | 10% | 20% | 15% |

### Recommended Extension Items

| Item | Reason |
|------|--------|
| IA15 | Tool-related queries frequently have voice search patterns |
| IA16 | Featured Snippet capture for tool definition queries is highly achievable |
| UX15 | Interactive content value is the core UX dimension for this profile |
| UX13 | Navigation within feature-heavy pages benefits from table of contents |
| GE12 | SoftwareApplication or WebApplication Schema increases tool discoverability |
| GE13 | Entity consistency is critical for SaaS brand/product knowledge graph presence |
| GE14 | Structured data completeness drives AI citation for tool recommendation queries |

### Scoring Notes

- GE pillar receives elevated weight (15%) because AI-powered search is increasingly used for tool discovery and recommendation queries.
- IA08 (Entity Salience Clarity) is critical: tool pages should be unambiguously "about" a single product/tool entity, not diluted across multiple products.
- FC pillar is de-weighted (10%) because tool pages have lower freshness decay risk than editorial content — the primary risk is outdated pricing or deprecated features (covered by FC04).
- IQ14 (Minimum Value Standard) requires that tool pages provide genuine text content around the tool — not just an interface with a headline.

---

## Profile 7: Comparison & Alternative

**Use when**: Content explicitly compares two or more products, tools, or services; or positions one product as an alternative to a named competitor.

**Typical formats**: "[Product A] vs [Product B]," "Best Alternatives to [Product X]," "Top 10 [Category] Tools Compared."

**Typical length**: 1,500–5,000 words.

**Examples**: "HubSpot vs Salesforce," "Best Notion Alternatives in 2025," "ActiveCampaign vs Mailchimp: Full Comparison."

### Pillar Weights

| IQ | EA | IA | FC | UX | GE |
|:--:|:--:|:--:|:--:|:--:|:--:|
| 15% | 25% | 20% | 15% | 15% | 10% |

### Recommended Extension Items

| Item | Reason |
|------|--------|
| IQ15 | Comparison tables with original benchmark data are the primary IGS driver |
| IQ06 | First-party testing data (own benchmark scores) is the highest-value differentiator |
| EA16 | No Deceptive Framing is especially critical — one-sided comparisons violate this |
| EA14 | Affiliate disclosure is mandatory and near-universal for comparison pages |
| FC04 | Product specs, pricing, and features change frequently — source currency is a major risk |
| FC15 | Comparison pages require visible changelogs as products update |
| GE05 | HTML comparison tables are the primary AI extraction asset for this format |
| GE11 | Comparison queries are high-value Featured Snippet targets |

### Scoring Notes

- **EA13 (Factual Accuracy) and EA16 (No Deceptive Framing) are the most consequential items for this profile.** Comparison pages that misrepresent competitor features, cherry-pick benchmark metrics, or use manipulative framing are both a trust failure and a policy risk (reference ARB PC04).
- The ARB PC04 boundary applies: comparison content must not make false claims about competitor products. Factual comparison is permissible; fabricated inferiority claims are not.
- IQ07 (Non-Obvious Perspective) is high-value: comparison pages that go beyond feature tables to provide genuine insight on use-case fit, migration difficulty, or total cost of ownership are consistently differentiated.
- FC04 (Source Currency) is a persistent risk: comparison pages with outdated pricing or deprecated features actively harm trust signals and should be on a quarterly review cadence.

---

## Profile 8: UGC & Community

**Use when**: Content is primarily generated by users, community members, or contributors — not by the site's editorial team. Includes forum threads, Q&A discussions, community answers, Reddit-style posts, and aggregated user reviews.

**Typical formats**: Forum thread, Q&A answer page, community discussion thread, aggregated user review page.

**Examples**: A Reddit-style discussion on "How do you deal with imposter syndrome?", Stack Overflow answer pages, Quora answer aggregations, product review aggregation pages.

### Pillar Weights

| IQ | EA | IA | FC | UX | GE |
|:--:|:--:|:--:|:--:|:--:|:--:|
| 25% | 30% | 15% | 10% | 10% | 10% |

### Profile-Specific Scoring Adjustments

UGC content operates under different structural assumptions from editorial content. The following scoring adjustments apply:

| Item | Adjustment |
|------|-----------|
| EA05 (Author Identity Visibility) | May be scored against the community's display name convention — full legal name not required if the community has established identity norms |
| EA07 (Methodological Transparency) | Not applicable to spontaneous UGC discussion; mark N/A |
| UX06 (Heading Hierarchy) | UGC threads often lack formal H-tag structure — score against thread navigation quality rather than HTML heading compliance |
| FC05 (Evergreen Language Discipline) | Not applicable for UGC discussion — mark N/A |
| GE12 (HowTo Schema) | Not applicable for discussion threads — mark N/A |

### Recommended Extension Items

| Item | Reason |
|------|--------|
| EA03 | Problems Encountered is the primary quality signal for UGC — real experience sharing is the core value |
| EA04 | Engagement Depth Statement: multi-reply threads with extended user participation are a quality signal |
| IQ09 | HCS alignment requires that UGC threads provide genuine discussion value, not spam or thin aggregation |
| IQ07 | Multi-perspective richness (non-obvious viewpoints from different community members) is the primary IQ differentiator |
| UX16 | Social proof (vote counts, reply counts, community validation) is the primary UX quality signal |
| FC16 | Source link audits are important for UGC threads with external citations |

### Scoring Notes

- **EA01–EA04 (Experience sub-group) are the highest-weighted items in this profile.** Google's "Hidden Gems" update and AI Overview sourcing preference explicitly favor authentic first-hand experience in UGC over polished but generic editorial content.
- IQ pillar receives the highest weight (25%) because the primary value of UGC content is information that cannot be found in official sources — real user experiences, workarounds, honest failures.
- The site operator's **moderation quality** is evaluated under IQ14 (Minimum Value Standard) — spam-heavy, unmoderated threads fail this item.
- UGC content is naturally lower on FC (10%) because temporal freshness is less critical than experience authenticity — a 3-year-old forum thread with genuine first-hand experience often outperforms a fresh but shallow editorial piece.

---

## Cross-Profile Conditional Extension Rules

When a content piece matches multiple profiles, apply these rules:

| Situation | Action |
|-----------|--------|
| Long-form Guide + YMYL | Use YMYL weights (EA at 30%); take union of all extension items from both profiles |
| Product Review + YMYL (e.g., supplement reviews) | Use YMYL weights; EA08 becomes veto; add EA18, IQ16, FC16 from YMYL profile |
| Comparison + Affiliate | Add EA14 and IQ13 as mandatory items; apply ARB PC10 disclosure check |
| How-to + News (breaking tutorial) | Use News weights for FC (25%); apply QDF response monitoring (FC13, FC14) |
| Tool + Comparison (tool comparison landing page) | Use Tool weights; add IQ15, GE05, GE13 from Comparison profile |
| Any profile + Multilingual site | Always add IA17 and GE16 regardless of base profile |

---

## Profile Selection Quick Reference

| Signal in Content | Most Likely Profile |
|-------------------|-------------------|
| First-person testing, hands-on assessment, "I tested…" | Product Review |
| Named competitor in title, "[X] vs [Y]" or "alternatives to…" | Comparison & Alternative |
| Date-stamped, news peg, breaking development | News & Trending |
| Numbered steps, "how to…" verb in title | How-to & Tutorial |
| Medical, financial, legal, safety topic | YMYL Content |
| Forum replies, community votes, user-submitted answers | UGC & Community |
| SaaS product, service page, interactive tool | Tool & Landing Page |
| Everything else (long educational resource) | Long-form Guide |
