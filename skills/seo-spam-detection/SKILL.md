---
name: seo-spam-detection
description: "Detect black-hat SEO techniques and spam indicators. Scans for keyword stuffing, hidden text, cloaking, spammy links, and other violations."
---

# SEO Spam Detection

Comprehensive detection of black-hat SEO techniques and spam indicators. Protects against policy violations and search penalties.

## Purpose

Audit for SEO spam:
- Detect keyword stuffing
- Find hidden text/links
- Identify cloaking techniques
- Flag spammy backlinks
- Detect comment spam
- Prevent search engine penalties

## Quick Start

**Input**: Website URL or source files
**Output**: Spam detection report + risk assessment
**Time**: 20-40 minutes

## Scoring Mode & Aggregation Contract

This skill is the main Search Integrity contributor and should align to the benchmark scope explicitly:

- `Core 79`: required coverage is SI01-SI12
- `Core 79 + Profile`: required coverage is SI01-SI12 plus any SI extension items selected by profile or trigger rules
- `Full 105`: cover SI01-SI16

Structured results should declare:
- `score_mode`
- `covered_items`
- `selected_profile_items` limited to SI items
- `triggered_extension_items` limited to SI items
- `manual_review_required` when evidence is directional but not conclusive

If this skill finds issues in SI13-SI16 while running `Core 79`, mark them as `extension_findings` so the aggregator can decide whether to widen scope.

---

## Keyword Stuffing Detection

### What is Keyword Stuffing?

Loading page with keywords unnaturally to improve rankings.

**Examples**:
- ❌ "Buy shoes, cheap shoes, best shoes, shoes online, discount shoes..."
- ❌ Repeating keyword 5+ times in 100 words
- ❌ Keywords unrelated to actual content

**Good Density** (~1-2% of words):
- 500-word article → 5-10 uses of keyword
- Natural language reads naturally

**Bad Density** (>5%):
- Keyword appears forced or repeated
- Sentences don't flow naturally
- Content feels spam-like

### Detection Process

**Manual Check**:
1. Read page naturally
2. Does it feel spam-like?
3. Are keywords forced?
4. Would actual user enjoy this?

**Automated Check**:
```javascript
function checkKeywordDensity(text, keyword) {
  const words = text.toLowerCase().split(/\s+/);
  const keywordCount = words.filter(
    word => word.includes(keyword.toLowerCase())
  ).length;

  const density = (keywordCount / words.length) * 100;

  // Red flags
  if (density > 5) return { spam: true, reason: 'High keyword density' };
  if (density > 3 && !naturalLanguage(text)) return { spam: true, reason: 'Forced keywords' };

  return { spam: false };
}
```

**Tools**:
- SEMrush Keyword Density
- Moz Keyword Tool
- SurferSEO density check

---

## Hidden Text & Links Detection

### Hidden Text Techniques

**Method 1: White Text on White Background**
```html
<div style="color: #fff; background: #fff;">
  keyword keyword keyword
</div>
```

**Method 2: Font Size 0**
```html
<div style="font-size: 0;">keyword spam</div>
```

**Method 3: Off-Page Positioning**
```css
.spam {
  position: absolute;
  left: -9999px; /* Off-screen */
}
```

**Method 4: Comments or Metadata**
```html
<!-- hidden keyword spam -->
<meta name="hidden" content="keyword spam">
```

### Detection

**Visual Check**:
1. Highlight all text on page
2. Look for invisible text
3. Check color contrast
4. Check font sizes

**Code Check**:
```bash
# Find suspicious CSS
grep -r "color: #fff" *.html
grep -r "font-size: 0" *.html
grep -r "left: -999" *.css
grep -r "display: none" *.css # If non-accessible
```

**Automated Check**:
```javascript
function findHiddenText(element) {
  const style = window.getComputedStyle(element);
  const issues = [];

  // Check visibility
  if (style.display === 'none') issues.push('Hidden with display:none');
  if (style.visibility === 'hidden') issues.push('Hidden with visibility:hidden');
  if (style.opacity === '0') issues.push('Hidden with opacity:0');

  // Check positioning
  const left = parseInt(style.left);
  if (left < -100) issues.push('Off-screen text');

  // Check color contrast
  const color = style.color;
  const bg = style.backgroundColor;
  if (contrast(color, bg) < 1) issues.push('No contrast (hidden)');

  return issues;
}
```

---

## Cloaking Detection

### What is Cloaking?

Showing different content to users vs. search engines.

**Example**:
- Googlebots see "Premium SEO Content"
- Users see "Click here for free money"

### Detection Process

**Check User-Agent**:
1. Crawl site as regular user
2. Crawl site as Googlebot
3. Compare responses
4. If different: 🚩 Cloaking detected

**Tools**:
- Google Search Console (Fetch as Google)
- SEMrush Site Audit
- Moz Crawl

**Manual Check**:
```bash
# Check as user
curl -H "User-Agent: Mozilla/5.0" https://example.com/page

# Check as Googlebot
curl -H "User-Agent: Mozilla/5.0 (compatible; Googlebot/2.1)" https://example.com/page

# Compare output (should be identical)
diff user-agent-response.html googlebot-response.html
```

---

## Spammy Backlinks Detection

### Red Flag Link Patterns

**Low-Quality Link Farms**:
- ❌ Links from directories with 10k+ sites
- ❌ Links from unrelated sites
- ❌ Links from known PBN (Private Blog Networks)
- ❌ Links with anchor text too similar to target keyword

**Unnatural Patterns**:
- ❌ 100 links added in 1 day
- ❌ Links from auto-generated sites
- ❌ Links from sites with 0 traffic
- ❌ Exact match anchor text 50%+ of links

### Analysis Process

**Step 1: Get Backlinks**
```bash
# Using SEMrush, Moz, Ahrefs, or similar:
# Export all backlinks to CSV
```

**Step 2: Categorize**
```
✅ Quality backlinks:
- News sites
- Industry publications
- Educational institutions
- High authority domains (DA >40)
- Natural, varied anchor text

⚠️ Questionable backlinks:
- Blogs that accept any content
- PBN indicators
- Exact match keywords 30-50%
- Recent bulk additions

❌ Spam backlinks:
- Obvious PBN (similar design/content)
- Exact match keywords 70%+
- Link farms
- Adult/gambling/pharmaceutical
- Automated comments
```

**Step 3: Analyze Patterns**
```javascript
function analyzeBacklinks(links) {
  let spam_score = 0;

  // Check anchor text ratio
  const exactMatch = links.filter(l => 
    l.anchor === targetKeyword
  ).length;
  if (exactMatch / links.length > 0.5) spam_score += 30;

  // Check domain authority
  const lowDA = links.filter(l => l.domainAuthority < 20).length;
  if (lowDA / links.length > 0.7) spam_score += 20;

  // Check diversity
  const uniqueDomains = new Set(links.map(l => l.domain)).size;
  if (uniqueDomains / links.length < 0.8) spam_score += 15;

  return spam_score;
}
```

### Disavow Bad Links

If you find spam links:
```
# Create disavow file
disavow.txt:
domain spam-site-1.com
domain spam-site-2.com
url https://bad-site.com/link-to-me

# Submit to Google Search Console
```

---

## Comment Spam Detection

### Red Flags

**Spam Comment Indicators**:
- Generic praise ("Great post!")
- Links in comment text
- Unrelated to content
- Multiple similar comments
- Foreign language comments
- Links to unrelated sites

### Prevention

**WordPress**:
- Enable Akismet (catches 90%+)
- Require approval
- Moderate comments
- Check for spammy URLs

**Custom Systems**:
```javascript
function isSpamComment(comment) {
  const spam_score = 0;

  // Generic praise
  if (/great post|nice article|thanks for sharing/.test(comment.text)) 
    spam_score += 20;

  // Links in comment
  if (comment.text.includes('http')) spam_score += 30;

  // Very short comment
  if (comment.text.length < 20) spam_score += 15;

  // All caps
  if (comment.text === comment.text.toUpperCase()) spam_score += 15;

  return spam_score > 50;
}
```

---

## SEO Spam Checklist

**Content**:
- [ ] No keyword stuffing (density <3%)
- [ ] No hidden text or links
- [ ] Natural, readable language
- [ ] Valuable to users

**Technical**:
- [ ] No cloaking for different user agents
- [ ] Same content for all users/crawlers
- [ ] No redirect tricks
- [ ] robots.txt not hiding content

**Links**:
- [ ] No unnatural link patterns
- [ ] Anchor text naturally varied
- [ ] No obvious PBN links
- [ ] Link growth normal/gradual

**Comments**:
- [ ] Comment spam moderated
- [ ] No spam links in comments
- [ ] Legitimate user discussion only

---

## Spam Detection Report

```markdown
# SEO Spam Detection Report

## Keyword Stuffing
- Pages analyzed: 150
- Keyword density average: 1.8%
- High density (>5%): 0 pages
- Suspicious patterns: 0
- Status: ✅ CLEAN

## Hidden Text/Links
- Pages scanned: 150
- Hidden text found: 0
- Off-screen content: 0
- Hidden links: 0
- Status: ✅ CLEAN

## Cloaking
- User-agent test: PASSED
- Content identical for all: ✅
- Googlebot sees same: ✅
- Status: ✅ CLEAN

## Backlink Analysis
- Total backlinks: 45
- Quality backlinks: 40 (89%)
- Questionable: 5 (11%)
- Spam backlinks: 0 (0%)
- Spam score: LOW

### Action Items
- Review 5 questionable links
- Disavow any confirmed spam

## Comment Spam
- Total comments: 320
- Spam detected: 3 (1%)
- Status: ✅ MINIMAL

## Overall Risk
- Risk level: LOW
- Recommendations: Monitor backlinks quarterly
```

---

## Automation Tools

**Built-In Options**:
- Google Search Console (organic search data)
- Google Analytics (spam traffic detection)
- Yoast SEO (WordPress plugin)

**Professional Tools**:
- SEMrush Site Audit
- Moz Pro
- Ahrefs
- Surfer SEO
- Screaming Frog

---

## Success Metrics

- [ ] Zero keyword stuffing
- [ ] Zero hidden text/links
- [ ] Zero cloaking indicators
- [ ] <5% spam backlinks
- [ ] Minimal comment spam
- [ ] No manual penalties from Google

---

**Related Skills**:
- Policy compliance → `policy-risk-scanner`
- Full audit → `ads-readiness-assessment`
- Monitoring → `active-compliance-monitor`
