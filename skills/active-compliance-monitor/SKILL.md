---
name: active-compliance-monitor
description: "Setup automated monitoring for ongoing AdSense compliance. Configure rules, alert thresholds, and monitoring workflows to detect and prevent violations post-approval."
---

# Active Compliance Monitor

Establish ongoing monitoring system for post-approval compliance. Detects violations early and triggers remediation workflows before Google enforcement action.

## Scope Context

Post-approval continuous monitoring layer. Re-runs audit skills on a schedule.

| Field | Value |
|---|---|
| **Phase** | Post-approval monitoring |
| **Recommended scope** | `Core 79 + Profile` for regular checks; `Full 105` for quarterly deep scans |
| **Monitored pillars** | All 6 (CI, PC, TH, UX, TD, SI) |
| **Score mode** | Declared per run; stored in monitoring log alongside timestamp |

Each monitoring run should record:
- `score_mode` used for that run
- `triggered_items`: ARB item IDs that flagged violations
- `severity`: Critical / High / Medium / Low
- Route Critical/High findings to the appropriate remediation skill immediately

## Purpose

Maintain compliance after AdSense approval:
- Monitor for policy violations in new content
- Track content quality metrics
- Detect spam/SEO violations
- Alert when ad code breaks
- Track performance metrics

## Implementation (Post-Approval)

### Month 1: Setup Foundation

**1. Content Policy Monitoring**

Monitor for prohibited content:
```
Keywords to flag (daily scan):
- Health misinformation: "cures cancer", "anti-vaccine"
- Adult content: [explicit terms]
- Illegal: "credit card numbers", "buy drugs"
- Hateful: [slurs and threats]
```

**2. Configuration**

Create `.monitoring/config.json`:
```json
{
  "monitors": [
    {
      "name": "Policy Violations",
      "frequency": "daily",
      "severity": "critical",
      "alert_to": ["admin@example.com"],
      "threshold": 1
    },
    {
      "name": "Performance Issues",
      "frequency": "weekly",
      "severity": "high",
      "alert_to": ["admin@example.com"],
      "threshold": 5
    }
  ]
}
```

**3. Alert Channels**

Setup notifications:
- [ ] Email alerts (daily/weekly summary)
- [ ] Slack integration (instant alerts)
- [ ] SMS for critical issues (optional)
- [ ] Dashboard for manual review

### Month 2: Content Quality Monitoring

**Monitor**:
- Content volume (thin page detection)
- Originality (duplication detection)
- Freshness (update frequency)
- Metadata quality (title/description)

**Implementation**:
```bash
# Daily content quality check
00 06 * * * /usr/local/bin/quality-monitor.sh > /tmp/quality.log
```

### Month 3: Ad Code Monitoring

**Monitor**:
- Ad code placement validation
- Ad unit count compliance
- Ad code errors in console
- AdSense revenue anomalies

**Implementation**:
```javascript
// Check ad code health
window.addEventListener('load', function() {
  if (!window.adsbygoogle) {
    console.error('AdSense code not loaded');
    alert_monitoring_system({
      issue: 'Ad code missing',
      severity: 'critical'
    });
  }
});
```

### Month 4: Advanced Metrics

**Monitor**:
- Click-through rate trends
- Cost per mille (CPM) trends
- Bounce rate changes
- Page load speed degradation

---

## Monthly Monitoring Checklist

```markdown
# Compliance Monitoring Checklist

## Daily (Automated)
- [ ] Scan new content for policy violations
- [ ] Check ad code errors
- [ ] Monitor server uptime
- [ ] Review analytics anomalies

## Weekly (Manual Review)
- [ ] Review flagged content
- [ ] Check click-through rates
- [ ] Verify affiliate disclosures still present
- [ ] Test page load speeds (5 random pages)

## Monthly (Full Audit)
- [ ] Content quality review (sample 20 pages)
- [ ] Affiliate disclosure audit
- [ ] Ad placement verification
- [ ] Performance metrics review
- [ ] Policy compliance spot-check

## Quarterly (Full Reassessment)
- [ ] Re-run ads-readiness-assessment
- [ ] Compare to baseline scores
- [ ] Identify improvement areas
- [ ] Update monitoring thresholds
```

---

## Alert Rules

### Critical Alerts (Immediate Action)

```
IF policy violation detected
  THEN email + Slack + block publication
  
IF ad code broken
  THEN email + SMS
  
IF revenue drops >30%
  THEN email + investigation flag
```

### High Priority Alerts (24-hour review)

```
IF new content has thin pages
  THEN email alert
  
IF duplicate content detected
  THEN email alert
  
IF site goes down for >5 minutes
  THEN email + SMS
```

---

## Success Metrics

- [ ] No policy violations post-approval
- [ ] No ad code issues detected
- [ ] Content quality maintained
- [ ] No unexpected rejections
- [ ] Revenue stable or growing

---

**Related Skills**:
- Health checks → `health-check-automation`
- Alert setup → `alert-rules-setup`
- Violations detected → Route to remediation guides
