---
name: copyright-ip-check
description: "Verify all content is original or properly licensed. Includes reverse image search, plagiarism checks, and copyright compliance verification."
---

# Copyright & IP Check

Comprehensive verification that all content is original or properly licensed. Protects against copyright infringement and IP violations.

## Scope Context

Audit-adjacent check. Contributes findings to CI and PC pillars.

| Field | Value |
|---|---|
| **Phase** | Audit (parallel to `content-audit`) |
| **ARB items covered** | CI05 (content originality), CI06 (duplicate detection), PC01 (illegal/IP infringement) |
| **Core 79 items** | CI05, CI06, PC01 (all core) |
| **Score mode** | Inherits from calling orchestrator; findings fed back into CI and PC pillar reports |

Findings from this skill should be merged into `content-audit` and `policy-risk-scanner` output (`items_evaluated`, `extension_findings`) when aggregated by `ads-readiness-assessment`.

## Purpose

Audit copyright compliance:
- Verify content originality
- Check image licenses
- Identify plagiarized content
- Verify permission for media
- Prevent copyright strikes
- Ensure compliance with content policies

## Quick Start

**Input**: Website URL or content files
**Output**: Originality report + license verification
**Time**: 30-60 minutes for full audit

---

## Content Originality Audit

### Step 1: Plagiarism Check

**Tool Options**:
1. **Copyscape Premium** ($4.99/check)
   - Best for full pages
   - Checks against web index
   - Also checks backups/cached

2. **Grammarly's Plagiarism Checker** ($free, limited)
   - Good for smaller checks
   - Limited monthly checks

3. **Turnitin** ($paid)
   - Most thorough
   - Academic standard

4. **Google Advanced Search**
   - Free alternative
   - Search for exact phrases

**Process**:
```bash
# For each page, copy-paste key sentences
# Search for exact phrase in Google
# If you're not first result, content may not be original

# Example search:
site:google.com "exact phrase from your content"
# If original content: You appear first
# If plagiarized: Others appear first
```

### Step 2: Manual Spot Check

Review random pages manually:
- Does this read naturally or feel generic?
- Are there unique examples or data?
- Is this unique perspective or repetition?
- Is it research or just summary?

**Red Flags**:
- ❌ Generic, templated-sounding content
- ❌ Overused phrases "In today's world..."
- ❌ No unique data or insights
- ❌ Similar structure to competitor pages
- ❌ Minimal value beyond summary

**Green Flags**:
- ✅ Unique examples or case studies
- ✅ Original research or data
- ✅ Personal experience and insights
- ✅ Unique structure and flow
- ✅ Specific details and nuance

---

## Image & Media Licensing

### Step 1: Identify All Images

**Inventory your images**:
```bash
find ./website -name "*.jpg" -o -name "*.png" -o -name "*.gif" -o -name "*.webp" | sort
```

### Step 2: Verify Each Image

**For each image, verify**:

**Option A: Original Images**
- [ ] You created it
- [ ] You have the raw files
- [ ] You own the copyright

**Option B: Licensed Images**
- [ ] From license-free source (Unsplash, Pexels)
- [ ] You have the license
- [ ] License allows commercial use
- [ ] Attribution required (if specified)

**Option C: Purchased License**
- [ ] From Shutterstock, Getty, Adobe Stock
- [ ] License covers your use
- [ ] Commercial license (not personal)
- [ ] Attribution required (if specified)

**Option D: Creative Commons**
- [ ] CC0 (public domain) 
- [ ] CC-BY (attribution required)
- [ ] CC-BY-SA (share-alike required)
- [ ] Proper attribution provided

**Option E: Used with Permission**
- [ ] Written permission obtained
- [ ] Keep documentation
- [ ] Follows usage terms

### Step 3: Reverse Image Search

Check if your images appear elsewhere:

```bash
# For each significant image:
# 1. Right-click → "Search image with Google"
# 2. See where else it appears
# 3. If primarily on your site: ✅ OK
# 4. If on many other sites: verify you have license

# Or use API:
# https://images.google.com (drag image in)
```

**What to Look For**:
- ✅ Image appears primarily on your site
- ✅ Older copies are attributed to you
- ⚠️ Image on few other licensed sites (check license)
- ❌ Image everywhere on unrelated sites (red flag)
- ❌ Image on competitor sites unchanged (likely violation)

### Step 4: Common Licensed Image Sources

**Free CC0 (Public Domain)**:
- Unsplash (unsplash.com)
- Pexels (pexels.com)
- Pixabay (pixabay.com)
- Burst by Shopify (burst.shopify.com)

**Free CC-BY (Attribution Required)**:
- Flickr (some images)
- Wikimedia Commons
- Pixabay (some images)

**Affordable Licensed**:
- Shutterstock (~$50-150/month)
- Adobe Stock (~$50-300/month)
- Getty Images (~$100+/month)
- Envato ($15-100 per image)

---

## Copyrighted Content Issues

### Issue 1: Scraped Content

**Signs**:
- Large blocks copied from other sites
- No original commentary
- Multiple sources combined without attribution

**Solution**:
1. Identify source content
2. Rewrite in your own words
3. Add original insights
4. Cite sources properly
5. Add 50%+ original content

### Issue 2: Unlicensed Images

**Signs**:
- Image appears on multiple unrelated sites
- High-quality stock photo appearance
- No source/attribution

**Solution**:
1. Replace with licensed image
2. Or purchase retroactive license
3. Or request permission from copyright holder
4. Remove if no license available

### Issue 3: Insufficient Attribution

**Required for CC-BY**:
- Creator's name
- License name/code
- Link to license
- Link to work (if applicable)

**Proper Attribution**:
```
"Photo by [Name] on [Source] under CC-BY license"
```

### Issue 4: Music/Audio

**Unlicensed Music**:
- Violates copyright
- YouTube claims videos
- Risk of strikes

**Licensed Music**:
- YouTube Audio Library (free)
- Epidemic Sound (~$100/month)
- Artlist (~$15/month)
- Royalty-free music sites

---

## Copyright Compliance Checklist

**Content**:
- [ ] 100% of text is original or properly licensed
- [ ] No large scraped/copied sections
- [ ] Plagiarism check shows <5% similarity
- [ ] All sources cited when needed
- [ ] No plagiarism from competitors

**Images**:
- [ ] 100% of images are original or licensed
- [ ] All licenses verified and compliant
- [ ] Commercial use is allowed
- [ ] Attribution provided when required
- [ ] Reverse image search confirms ownership

**Media**:
- [ ] All audio/video properly licensed
- [ ] Music licensed for commercial use
- [ ] Video clips have permission
- [ ] No unlicensed third-party content

**Legal**:
- [ ] Copyright notice visible (© Year Name)
- [ ] Trademark symbols used correctly
- [ ] No trademark violations
- [ ] License/attribution statements clear

---

## Audit Report Template

```markdown
# Copyright & IP Compliance Report

## Content Originality
- Pages audited: 50
- Plagiarism check: 48/50 passed (<5% similarity)
- Manual review: 45/50 original content
- Issues found: 5 pages require attention
- Status: ⚠️ NEEDS FIXES

## Critical Issues
1. Blog post "Top Tools" - 40% similar to [competitor]
   Action: Rewrite and add unique examples
2. Page "Getting Started" - scraped from [source]
   Action: Rewrite with original content

## Image Licensing
- Total images: 125
- Licensed/Original: 120 (96%)
- Questionable: 5 (4%)
- Status: ⚠️ MINOR ISSUES

### Questionable Images
1. Image001.png - No clear source
   Action: Replace with licensed image
2. Image042.jpg - No license verification
   Action: Verify license or replace

## Overall Status
- Content: ⚠️ 2 pages need rewriting
- Images: ✅ 1 image needs replacement
- Risk Level: LOW

## Action Timeline
1. Rewrite 5 content pages (week 1)
2. Replace 5 images (week 1)
3. Verify all licenses again (week 2)
4. Re-audit (week 2)
```

---

## Automation Script

**Plagiarism scanner**:
```javascript
const fs = require('fs');
const fetch = require('node-fetch');

async function checkPlagiarism(text) {
  // Extract key sentences
  const sentences = text.split('.')
    .filter(s => s.trim().length > 50)
    .slice(0, 5); // Check first 5 long sentences

  const results = [];

  for (const sentence of sentences) {
    // Use Copyscape API or similar
    // For demo: log sentences to check manually
    console.log(`Check: "${sentence.trim()}"`);
  }

  return results;
}

async function checkImageLicenses(imageUrls) {
  // For each image URL
  // Use Google Images reverse search
  // Or Tineye API for programmatic check
  
  const tinyeApiKey = process.env.TINEYE_API_KEY;
  // Implementation would use TinEye or similar
}
```

---

## Legal Protection

**If you find violation**:
1. Immediately cease the violation
2. Document changes made
3. Add proper attribution/license
4. Keep records of remediation
5. Monitor for recurrence

**If someone violates YOUR copyright**:
1. Send cease & desist letter
2. File DMCA takedown (if on web)
3. Contact YouTube/platform (if video)
4. Consult lawyer for serious violations

---

## Success Metrics

- [ ] 100% content is original or properly licensed
- [ ] <5% plagiarism for all pages
- [ ] 100% images have verified licenses
- [ ] 0 copyright complaints received
- [ ] All attribution accurate and prominent

---

**Related Skills**:
- Policy compliance → `policy-risk-scanner`
- Full audit → `ads-readiness-assessment`
- Monitoring → `active-compliance-monitor`
