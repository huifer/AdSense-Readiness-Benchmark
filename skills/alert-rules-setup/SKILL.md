---
name: alert-rules-setup
description: "Configure multi-channel alert system. Setup email, Slack, and webhook notifications for policy violations, performance issues, and compliance problems."
---

# Alert Rules Setup

Configure automated alert system to notify you of issues immediately. Supports email, Slack, webhooks, and SMS.

## Scope Context

Configuration skill for `active-compliance-monitor` alerts.

| Field | Value |
|---|---|
| **Phase** | Post-approval configuration |
| **Depends on** | `active-compliance-monitor` |
| **ARB item coverage** | Alert thresholds should map to ARB item severity levels (Critical → immediate, High → same-day, Medium → weekly) |
| **Score mode** | Inherits from `active-compliance-monitor` run config; alerts should record which score mode triggered them |

Alert configurations should include the `score_mode` of the monitoring run so teams know which item set is being watched.

## Purpose

Real-time notification for:
- Policy violations
- Ad code issues
- Performance degradation
- Revenue anomalies
- Site health problems

## Quick Setup (Choose One)

### Option 1: Email Alerts (Simplest)

**Create** `alerts-config.json`:
```json
{
  "alerts": [
    {
      "name": "Policy Violation",
      "condition": "policy_violation_found",
      "severity": "critical",
      "email": "admin@example.com",
      "frequency": "instant"
    },
    {
      "name": "Performance Drop",
      "condition": "lcp_> 3000",
      "severity": "high",
      "email": "admin@example.com",
      "frequency": "daily"
    }
  ]
}
```

**Script** (Node.js):
```javascript
const nodemailer = require('nodemailer');

const transporter = nodemailer.createTransport({
  service: 'gmail',
  auth: {
    user: process.env.EMAIL_USER,
    pass: process.env.EMAIL_PASSWORD
  }
});

async function sendAlert(alert) {
  await transporter.sendMail({
    from: 'alerts@example.com',
    to: alert.email,
    subject: `[${alert.severity}] ${alert.name}`,
    html: `<h2>${alert.name}</h2><p>${alert.message}</p>`
  });
}
```

---

### Option 2: Slack Alerts (Recommended)

**Setup**:
1. Create Slack App at api.slack.com
2. Enable "Incoming Webhooks"
3. Create webhook URL: `https://hooks.slack.com/...`

**Script**:
```javascript
const axios = require('axios');

async function sendSlackAlert(message, severity = 'warning') {
  const color = severity === 'critical' ? 'danger' : 'warning';
  
  await axios.post(process.env.SLACK_WEBHOOK, {
    attachments: [{
      color: color,
      title: message.title,
      text: message.description,
      fields: [
        { title: 'Severity', value: severity, short: true },
        { title: 'Time', value: new Date().toISOString(), short: true }
      ]
    }]
  });
}

// Usage
sendSlackAlert({
  title: 'Policy Violation Detected',
  description: 'Page /blog/health contains prohibited health claim'
}, 'critical');
```

---

### Option 3: Google Sheets Integration

**Auto-log alerts to Google Sheet**:
```javascript
const { google } = require('googleapis');

async function logAlertToSheet(alert) {
  const sheets = google.sheets_v4.spreadsheets();
  
  await sheets.values.append({
    spreadsheetId: process.env.SHEET_ID,
    range: 'Alerts!A1',
    valueInputOption: 'USER_ENTERED',
    resource: {
      values: [[new Date(), alert.type, alert.severity, alert.message]]
    }
  });
}
```

---

## Alert Rules

### Critical Alerts

```
Rule: Policy Violation Detected
Trigger: New content contains prohibited keywords
Action: Email + Slack + Block publication
Response Time: Immediate
```

```
Rule: Ad Code Broken
Trigger: Ad code errors in console
Action: Email + SMS + Alert dashboard
Response Time: Immediate
```

```
Rule: Site Down
Trigger: Site status code != 200 for 5+ minutes
Action: SMS + Email + Pagerduty
Response Time: Immediate
```

### High Priority Alerts

```
Rule: Thin Page Published
Trigger: New page <300 words
Action: Email alert
Response Time: 1 hour
```

```
Rule: Performance Degradation
Trigger: LCP > 3 seconds or CLS > 0.25
Action: Email alert
Response Time: 4 hours
```

```
Rule: Duplicate Content
Trigger: New content >80% similar to existing
Action: Email alert
Response Time: Daily digest
```

### Medium Priority Alerts

```
Rule: Affiliate Disclosure Missing
Trigger: New post with affiliate links but no disclosure
Action: Email alert
Response Time: Daily digest
```

```
Rule: Broken Links
Trigger: Internal links returning 404
Action: Weekly digest
Response Time: Weekly
```

---

## Setup by Provider

### AWS SNS + Lambda

```javascript
const AWS = require('aws-sdk');
const sns = new AWS.SNS();

exports.handler = async (event) => {
  await sns.publish({
    TopicArn: process.env.SNS_TOPIC,
    Subject: 'AdSense Alert',
    Message: JSON.stringify(event.alert)
  }).promise();
};
```

### Prometheus + Alertmanager

```yaml
groups:
  - name: adsense
    rules:
      - alert: PolicyViolation
        expr: policy_violations > 0
        annotations:
          summary: "Policy violation detected"
```

### Datadog

```javascript
const dogapi = require('dogapi');

dogapi.event.create({
  title: 'Policy Violation',
  text: 'Prohibited content found on /blog/health',
  priority: 'high',
  alert_type: 'error'
});
```

---

## Alert Rules Configuration

```json
{
  "alert_rules": [
    {
      "id": "policy_violation",
      "name": "Policy Violation",
      "severity": "critical",
      "conditions": [
        "policy_violation_found = true"
      ],
      "actions": [
        "email",
        "slack",
        "block_publication"
      ],
      "recipients": {
        "email": ["admin@example.com"],
        "slack": ["#alerts"]
      }
    },
    {
      "id": "performance_degrade",
      "name": "Performance Degradation",
      "severity": "high",
      "conditions": [
        "lcp > 3000 ms",
        "cls > 0.25"
      ],
      "actions": ["email"],
      "recipients": {
        "email": ["admin@example.com"]
      }
    }
  ]
}
```

---

## Alert Response Procedures

### For Critical Alerts (Respond Immediately)

1. **Policy Violation**
   - Review flagged content
   - Remove or revise immediately
   - Update robots.txt if needed
   - Request re-review if necessary

2. **Ad Code Broken**
   - Check error message
   - Verify ad code in place
   - Check browser console
   - Re-implement if needed

3. **Site Down**
   - Check server status
   - Verify DNS is working
   - Check hosting provider status
   - Restore if backup available

### For High Priority Alerts (Respond within 4 hours)

1. **Thin Page**
   - Expand content to 300+ words
   - Add examples/details
   - Re-verify if needed

2. **Performance Issue**
   - Optimize images
   - Enable compression
   - Implement CDN
   - Test and verify improvements

### For Medium Priority Alerts (Respond within 24 hours)

1. **Missing Disclosures**
   - Add affiliate/sponsored disclosure
   - Re-publish content

2. **Broken Links**
   - Fix links to working pages
   - Or implement 301 redirects

---

## Escalation Policy

| Severity | Initial Response | Escalation | Owner |
|----------|------------------|-----------|-------|
| Critical | <5 min           | 30 min    | Admin |
| High     | <1 hour          | 4 hours   | Team  |
| Medium   | <4 hours         | 1 day     | Team  |
| Low      | <1 day           | 1 week    | Queue |

---

## Testing Alerts

**Test email alert**:
```bash
curl -X POST http://localhost:8000/test-alert \
  -H "Content-Type: application/json" \
  -d '{"type":"policy_violation"}'
```

**Verify Slack connection**:
```bash
curl -X POST $SLACK_WEBHOOK \
  -d '{"text":"Test alert"}'
```

**Load test alerts**:
```bash
for i in {1..10}; do
  npm run test-alert
  sleep 2
done
```

---

## Success Metrics

- [ ] All alerts triggering correctly
- [ ] Response time <5 min for critical alerts
- [ ] No false positives (>80% true alert rate)
- [ ] No missed alerts (>95% detection rate)
- [ ] Team responding within SLA

---

**Related Skills**:
- Compliance monitoring → `active-compliance-monitor`
- Health checks → `health-check-automation`
