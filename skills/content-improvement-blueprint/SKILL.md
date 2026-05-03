---
name: content-improvement-blueprint
description: "Actionable guide to fix Content Integrity (CI) violations. Includes rewriting strategies, volume expansion, originality improvement, metadata optimization with detailed examples."
---

# Content Improvement Blueprint

Step-by-step guide to improve your content based on violations found by `content-audit`. Provides specific rewriting strategies, examples, and actionable improvements for every CI criterion.

## Scope Context

Downstream remediation skill fed by `content-audit`.

| Field | Value |
|---|---|
| **Phase** | Remediation |
| **Upstream** | `content-audit` |
| **ARB items addressed** | CI01–CI14 (core); CI15–CI18 when flagged as extension |
| **Score mode** | Inherited from `content-audit` output — this skill does not independently score |

Improvements made here must be re-verified by running `content-audit` again under the **same score mode** to confirm items now pass.

## Purpose

Transform content audit violations into concrete improvements:
- Expand thin content to meet volume requirements
- Improve originality and reduce duplication
- Enhance metadata (titles, descriptions)
- Fix heading structure and content formatting
- Increase content freshness and update frequency
- Add proper multimedia captions and context

## Quick Start

**Input**: Content audit violations report (from `content-audit`)
**Output**: Detailed improvement guide + rewriting examples + priority action list
**Time**: 2-6 hours to execute for typical site

## Workflow

### Step 1: Prioritize Violations

Review audit violations and prioritize by impact:
1. **Critical** (blocks approval): Thin pages, extensive duplication, missing metadata
2. **High**: Originality issues, heading problems, AI content without value-add
3. **Medium**: Metadata optimization, freshness updates
4. **Low**: Formatting improvements, multimedia enhancements

### Step 2: Expand Thin Content (CI01)

If pages are under 300 words:

**Strategy 1: Add Examples**
- Industry-specific examples
- Case studies or success stories
- Real-world applications
- Step-by-step walkthroughs

**Strategy 2: Provide More Detail**
- Expand on key concepts
- Add reasoning and explanation
- Include pros/cons analysis
- Link to related topics

**Strategy 3: Answer Common Questions**
- FAQ section
- Troubleshooting guide
- Common misconceptions
- Expected outcomes

**Example**:
```
BEFORE (150 words):
"To plant a tree, dig a hole, put the tree in, and cover with soil."

AFTER (350+ words):
"To plant a tree successfully:
1. Choose the right location (sun, drainage, space)
2. Prepare the soil (loosen, add amendments)
3. Dig a hole 2-3x the root ball
4. Place tree carefully, keeping roots intact
5. Cover with soil, compress gently
6. Water thoroughly and add mulch
7. Water regularly first year
8. Common mistakes to avoid...
9. Timeline for growth...
10. Species-specific considerations..."
```

### Step 3: Improve Originality (CI02)

If content has duplication issues:

**Strategy 1: Rewrite in Your Voice**
- Use different sentence structures
- Add your unique perspective
- Include personal experience or expertise
- Cite your own research or observations

**Strategy 2: Add Unique Value**
- Original data or research
- Unique analysis or insights
- Proprietary frameworks or methods
- Original examples or case studies

**Strategy 3: Consolidate or Link**
- Merge similar content into one authoritative page
- Use internal linking to connect related content
- Create unique angles for each page
- Avoid word-for-word repetition

**Example**:
```
BEFORE (from Wikipedia):
"Python is a high-level, general-purpose programming language."

AFTER (Your version):
"We chose Python for our data analysis platform because
of its data science libraries and readability. Here's how
it compares to our previous stack..."
```

### Step 4: Optimize Metadata (CI11, CI12)

**Improve Meta Descriptions**:

**Rules**:
- 120-158 characters
- Unique per page
- Include primary keyword
- Call-to-action or benefit
- Accurate summary of page content

**Template**:
`[Benefit/Problem] + [Primary Keyword] + [CTA]`

**Examples**:

```
BEFORE:
"This page is about gardening"

AFTER (100% better):
"Learn 10 proven gardening techniques to grow organic
vegetables in any climate. Complete beginner's guide."

BEFORE:
"Blog post"

AFTER:
"Discover why your plants are dying. Expert tips for
diagnosing plant diseases and saving your garden."
```

**Improve Title Tags**:

**Rules**:
- 50-60 characters (ideal)
- Unique per page
- Primary keyword near start
- Compelling and accurate
- Brand name optional (if space)

**Templates**:
- `Primary Keyword | Benefit - Brand`
- `How to [Primary Keyword] - Step-by-Step Guide`
- `[Primary Keyword] 101: Complete Guide for [Audience]`

**Examples**:

```
BEFORE:
"Home Gardening Tips"

AFTER:
"Organic Vegetable Gardening | Complete Beginner Guide"
"How to Grow Tomatoes - 10 Proven Tips"

BEFORE:
"Digital Marketing Blog Post"

AFTER:
"SEO for Beginners: 15-Step Checklist"
"Email Marketing Strategy | Increase Sales by 40%"
```

### Step 5: Fix Heading Structure (CI13)

**Rules**:
- Exactly one H1 per page
- Logical nesting: H1 → H2 → H3 (no skips)
- All headings relevant to content
- Clear hierarchy

**Before/After**:

```html
BEFORE (Wrong):
<h1>Main Title</h1>
<h1>Another Title</h1>
<h3>Missing H2</h3>

AFTER (Correct):
<h1>Main Topic</h1>
<h2>Section 1</h2>
<h3>Subsection 1.1</h3>
<h3>Subsection 1.2</h3>
<h2>Section 2</h2>
<h3>Subsection 2.1</h3>
```

### Step 6: Improve Content Freshness (CI05, CI15)

**For High-Value Pages (How-to, Reviews)**:
- Should be updated within 12 months
- Mark update date prominently
- Add "Last Updated: [Date]"
- Refresh statistics and examples

**For Evergreen Content**:
- Update quarterly minimum
- Add new examples or case studies
- Update expired links and references
- Refresh outdated screenshots

**Freshness Checklist**:
- [ ] Review all statistics and data (cite sources <2 years)
- [ ] Update product links and pricing
- [ ] Refresh screenshots (technology changes)
- [ ] Add new examples or case studies
- [ ] Fix broken internal links
- [ ] Add "Last Updated" date
- [ ] Review comments and address questions

### Step 7: Structure Content Better (CI14)

**Add Visual Breaks**:

```markdown
BEFORE (Wall of text):
This technique is useful. You should try it. Many people
have found it effective. To do it, you need to follow
several steps. First you do this...

AFTER (Structured):
This technique is useful and effective for most people.

## How to Get Started

1. Step one
2. Step two
3. Step three

## Pro Tips

- Tip A
- Tip B
- Tip C

| Comparison | Value A | Value B |
|-----------|---------|---------|
| Metric 1  | X       | Y       |
```

### Step 8: Handle AI-Generated Content (CI08)

If content is AI-generated:

**Add Unique Value**:
- Your own data or research findings
- Personal experience or case studies
- Original analysis or framework
- Unique examples or comparisons
- Expert commentary or critique

**Example**:
```
AI-generated content about "How to Write Blog Posts"
ADD: Your proven formula, real examples from your blog,
     your specific process, mistakes you made
```

### Step 9: Verify Multimedia (CI18)

For any embedded videos/audio:

**Add**:
- Transcript or captions
- Text summary
- Original context or commentary
- Why this media is relevant

**Example**:
```html
<video src="..." controls>
  <track kind="captions" src="captions.vtt" srclang="en">
</video>

<h3>Video Summary</h3>
<p>In this video, John explains...</p>

<h3>Key Takeaways</h3>
<ul>
  <li>...</li>
</ul>
```

## Prioritized Action Plan

### Week 1: Critical Fixes
- [ ] Identify pages with CI01 violations (thin content <300 words)
- [ ] Expand 3-5 highest-traffic thin pages to 300+ words
- [ ] Fix major duplication (CI02) by consolidating or rewriting
- [ ] Fix critical heading structure issues (CI13)

### Week 2: Metadata & Structure
- [ ] Write unique, optimized meta descriptions (20-30 pages)
- [ ] Optimize title tags (20-30 pages)
- [ ] Add proper heading structure to key pages
- [ ] Format content with lists, tables, bullet points

### Week 3: Freshness & Updates
- [ ] Update high-value pages with current data
- [ ] Add "Last Updated" dates to fresh content
- [ ] Fix outdated links and examples
- [ ] Refresh screenshots or imagery

### Week 4: Verification
- [ ] Re-run content-audit to verify fixes
- [ ] Test metadata in search results preview
- [ ] Check heading structure with SEO tools
- [ ] Verify all multimedia has captions/context

## Common Improvements by Issue

### Thin Pages (CI01)
**Minimum 300 words** - Focus on depth, not padding
- What, Why, How structure
- Examples and case studies
- FAQ addressing user questions
- Related resources
- Actionable next steps

**Target**: 500-1500 words for most topics

### Duplication (CI02, CI07)
**Detect**: Content audit shows >80% overlap
- Rewrite in your voice
- Consolidate into single authoritative page
- Create different angles for different audiences
- Add unique perspectives or data

**Target**: Unique perspective on each page

### Thin Metadata (CI11, CI12)
**Fix in**: 5-10 minutes per page
- Write specific, benefit-focused meta descriptions
- Use primary keywords naturally
- Keep titles between 50-60 characters
- Include compelling language

**Result**: Click-through rate improvement 10-30%

### Poor Structure (CI13, CI14)
**Fix in**: 10-30 minutes per page
- Add H2/H3 headings
- Create scannable content with lists
- Add tables for comparisons
- Use bold for key points
- Add whitespace

**Result**: 20-40% improvement in readability

### Outdated Content (CI05, CI15)
**Review**: Quarterly for evergreen content, yearly minimum
- Update statistics and citations
- Add new examples
- Refresh screenshots
- Add "Last Updated" date
- Link to related new content

**Result**: Regain ranking for updated content

## Output Formats

### Markdown Improvement Guide
```markdown
# Content Improvement Blueprint

## Priority 1: Thin Pages (CI01)
- Blog: "10 Tips" (120 words) → Expand to 400+ words
- Guide: "Getting Started" (180 words) → Add FAQ section

## Priority 2: Metadata (CI11, CI12)
- Rewrite 45 meta descriptions
- Optimize 45 title tags

## Priority 3: Freshness (CI05)
- Update "2023 Trends" article with 2025 data
- Add "Last Updated" dates to 20 posts

## Rewriting Examples
[Detailed before/after examples...]
```

### Action Checklist
```csv
Page,Issue,Priority,Action,Status,Time
/blog/tips,CI01,High,Expand to 400+,To Do,2h
/guides/start,CI11,Medium,Rewrite meta,To Do,30m
/about,CI05,Low,Update date,To Do,15m
```

### Content Templates
- Meta description templates
- Title tag formulas
- Heading structure templates
- Content outline templates

## Integration

```
Consumed from: [content-audit]
Provides input to: [resubmission-readiness-check]
Re-verified by: [content-audit] (re-run after fixes)
```

## Tips for Success

1. **Don't Keyword Stuff**: Write naturally for users
2. **Add Value**: Make content genuinely useful
3. **Use Your Voice**: Original perspective matters
4. **Show Expertise**: Cite sources and data
5. **Keep Fresh**: Update regularly
6. **Format Well**: Make scannable and readable
7. **Link Wisely**: Internal links help Google understand
8. **Test Metadata**: Preview in search results

## Next Steps

1. Complete actions in priority order (Week 1-4)
2. Re-run `content-audit` to verify improvements
3. Monitor Google Search Console for ranking changes
4. Measure click-through rate improvements
5. Track user engagement metrics
6. Use `resubmission-readiness-check` before final submission

---

**Related Skills**:
- Audit results → `content-audit`
- Verify fixes → `resubmission-readiness-check`
- Full site review → `ads-readiness-assessment`
