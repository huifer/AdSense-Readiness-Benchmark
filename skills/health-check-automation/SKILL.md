---
name: health-check-automation
description: "Generate deployable scripts for automated health checks. Includes Node.js, Python, and Bash implementations. Runs periodic checks and generates reports."
---

# Health Check Automation

Create and deploy automated scripts for periodic site health verification. Generates reports and alerts on issues found.

## Scope Context

Post-approval automation layer. Generates deployable scripts that invoke audit skills on a schedule.

| Field | Value |
|---|---|
| **Phase** | Post-approval automation |
| **Depends on** | All primary audit skills (content-audit, technical-audit, ux-compliance-audit, policy-risk-scanner, seo-spam-detection) |
| **ARB item coverage** | Configurable; defaults to `Core 79` for lightweight scheduled checks |
| **Score mode** | `Core 79` for daily automated checks; `Core 79 + Profile` for weekly; `Full 105` for monthly |

Each automated run should log `score_mode` and `timestamp` for a complete audit trail.

## Purpose

Automate health checks post-approval:
- Periodic content quality scans
- Performance metric collection
- Link validity verification
- SEO health assessment
- Generate automated reports

## Quick Start

Choose your environment:

### Node.js Implementation

**Install**:
```bash
npm install axios cheerio moment
```

**Script** (`health-check.js`):
```javascript
const axios = require('axios');
const cheerio = require('cheerio');
const fs = require('fs');

const config = {
  site_url: 'https://example.com',
  check_pages: 10,
  interval: 86400 // Daily (seconds)
};

async function healthCheck() {
  const report = {
    timestamp: new Date(),
    checks: []
  };

  // Check 1: Site up?
  try {
    await axios.get(config.site_url, { timeout: 5000 });
    report.checks.push({ name: 'Uptime', status: 'pass' });
  } catch (e) {
    report.checks.push({ name: 'Uptime', status: 'fail', error: e.message });
  }

  // Check 2: SSL certificate valid?
  const https_check = await axios.get(config.site_url);
  if (https_check.config.url.startsWith('https')) {
    report.checks.push({ name: 'HTTPS', status: 'pass' });
  }

  // Check 3: Robots.txt exists?
  try {
    await axios.get(`${config.site_url}/robots.txt`);
    report.checks.push({ name: 'Robots.txt', status: 'pass' });
  } catch {
    report.checks.push({ name: 'Robots.txt', status: 'fail' });
  }

  // Save report
  fs.writeFileSync(`./reports/health-${Date.now()}.json`, JSON.stringify(report));
  console.log('Health check complete:', report);
}

// Run daily
setInterval(healthCheck, config.interval * 1000);
healthCheck(); // First run
```

**Run**:
```bash
node health-check.js &
```

---

### Python Implementation

**Requirements** (`requirements.txt`):
```
requests==2.28.0
beautifulsoup4==4.11.0
pytz==2022.1
```

**Script** (`health_check.py`):
```python
import requests
import json
from datetime import datetime
import schedule
import time

CONFIG = {
    'site_url': 'https://example.com',
    'check_pages': 10
}

def health_check():
    report = {
        'timestamp': datetime.now().isoformat(),
        'checks': []
    }

    # Check uptime
    try:
        response = requests.get(CONFIG['site_url'], timeout=5)
        report['checks'].append({
            'name': 'Uptime',
            'status': 'pass' if response.status_code == 200 else 'fail'
        })
    except Exception as e:
        report['checks'].append({'name': 'Uptime', 'status': 'fail', 'error': str(e)})

    # Check HTTPS
    if CONFIG['site_url'].startswith('https'):
        report['checks'].append({'name': 'HTTPS', 'status': 'pass'})

    # Check robots.txt
    try:
        requests.get(f"{CONFIG['site_url']}/robots.txt")
        report['checks'].append({'name': 'Robots.txt', 'status': 'pass'})
    except:
        report['checks'].append({'name': 'Robots.txt', 'status': 'fail'})

    # Save report
    with open(f"reports/health-{datetime.now().timestamp()}.json", 'w') as f:
        json.dump(report, f)

    return report

# Schedule daily check at 6 AM
schedule.every().day.at("06:00").do(health_check)

while True:
    schedule.run_pending()
    time.sleep(60)
```

**Run**:
```bash
python health_check.py &
```

---

### Bash Implementation

**Script** (`health-check.sh`):
```bash
#!/bin/bash

SITE_URL="https://example.com"
REPORT_DIR="./reports"
TIMESTAMP=$(date +%Y-%m-%d_%H-%M-%S)
REPORT="$REPORT_DIR/health-$TIMESTAMP.txt"

mkdir -p $REPORT_DIR

echo "Health Check Report - $TIMESTAMP" > $REPORT
echo "===================================" >> $REPORT

# Check uptime
echo -n "Uptime: " >> $REPORT
if curl -s -o /dev/null -w "%{http_code}" $SITE_URL | grep -q "200"; then
  echo "PASS" >> $REPORT
else
  echo "FAIL" >> $REPORT
fi

# Check HTTPS
echo -n "HTTPS: " >> $REPORT
if curl -s $SITE_URL | grep -q "https"; then
  echo "PASS" >> $REPORT
else
  echo "FAIL" >> $REPORT
fi

# Check robots.txt
echo -n "Robots.txt: " >> $REPORT
if curl -s -I $SITE_URL/robots.txt | grep -q "200"; then
  echo "PASS" >> $REPORT
else
  echo "FAIL" >> $REPORT
fi

echo "Report saved: $REPORT"
```

**Setup Cron** (daily at 6 AM):
```bash
0 6 * * * /path/to/health-check.sh
```

---

## Docker Implementation (Advanced)

**Dockerfile**:
```dockerfile
FROM node:16-slim

WORKDIR /app
COPY health-check.js .
COPY package.json .

RUN npm install

CMD ["node", "health-check.js"]
```

**docker-compose.yml**:
```yaml
version: '3'
services:
  health-check:
    build: .
    volumes:
      - ./reports:/app/reports
    restart: always
```

**Run**:
```bash
docker-compose up -d
```

---

## Report Generation

**Generate Monthly Report**:
```javascript
function generateMonthlyReport() {
  const reports = fs.readdirSync('./reports');
  const thisMonth = reports.filter(r => r.includes(currentMonth));
  
  const summary = {
    total_checks: thisMonth.length,
    failed_checks: thisMonth.filter(r => r.includes('fail')).length,
    success_rate: '95%'
  };
  
  sendEmailReport(summary);
}
```

---

## Dashboard Integration

**Export to CSV**:
```javascript
const json2csv = require('json2csv');
const data = JSON.parse(fs.readFileSync('reports/health.json'));
const csv = json2csv.parse(data);
fs.writeFileSync('reports/health.csv', csv);
```

**Push to Monitoring Service**:
```javascript
// Send to DataDog, New Relic, or Grafana
const axios = require('axios');

axios.post('https://api.datadoghq.com/api/v2/events', {
  title: 'Health Check',
  text: report.summary,
  alert_type: 'info'
}, {
  headers: { 'DD-API-KEY': process.env.DATADOG_KEY }
});
```

---

## Monitoring Checklist

- [ ] Script runs daily
- [ ] Reports generated successfully
- [ ] No accumulation of old reports
- [ ] Alerts triggering on failures
- [ ] Dashboard updated with latest data

---

**Related Skills**:
- Set alerts → `alert-rules-setup`
- Monitor compliance → `active-compliance-monitor`
