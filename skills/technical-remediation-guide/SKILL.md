---
name: technical-remediation-guide
description: "Actionable guide to fix Technical Health (TH) violations. Includes HTTPS setup, performance optimization, mobile fixes, structured data, and server configuration with code examples."
---

# Technical Remediation Guide

Step-by-step solutions for all Technical Health violations. Provides configuration code, performance optimization strategies, and setup procedures for developers and site administrators.

## Scope Context

Downstream remediation skill fed by `technical-audit`.

| Field | Value |
|---|---|
| **Phase** | Remediation |
| **Upstream** | `technical-audit` |
| **ARB items addressed** | TH01–TH13 (core); TH14–TH20 when flagged as extension |
| **Score mode** | Inherited from `technical-audit` output — this skill does not independently score |
| **Veto priority** | TH01 (HTTPS) is a veto item — fix before all other TH items |

Fixes must be re-verified by running `technical-audit` again under the **same score mode**.

## Purpose

Fix technical issues found by `technical-audit`:
- Enable HTTPS/SSL
- Improve Core Web Vitals and performance
- Mobile responsiveness
- Structured data implementation
- Server configuration (CDN, compression, caching)

## Quick Start

**Input**: Technical audit violations (from `technical-audit`)
**Output**: Code snippets + configuration guides + step-by-step procedures
**Time**: 4-20 hours depending on issues

## Critical Fixes (Must Do First)

### HTTPS/SSL (TH01) — CRITICAL BLOCKER

**Check Status**:
```bash
# Test if site is HTTPS
curl -I https://example.com
curl -I http://example.com
```

**Fix - Option 1: Cloud Provider (Easiest)**
- If on Cloudflare: Enable "Always HTTPS" + "Full SSL"
- If on AWS: Use ACM certificate + ALB
- If on Heroku: Automatic with herokuapp.com domain
- If on Netlify/Vercel: Automatic

**Fix - Option 2: Self-Hosted**

1. Obtain SSL certificate:
```bash
# Option A: Let's Encrypt (Free, recommended)
sudo apt-get install certbot python3-certbot-nginx
sudo certbot certonly --nginx -d example.com

# Option B: Buy from CA (GoDaddy, Digicert, etc.)
```

2. Configure NGINX:
```nginx
server {
    listen 443 ssl http2;
    server_name example.com;
    
    ssl_certificate /path/to/cert.pem;
    ssl_certificate_key /path/to/key.pem;
    ssl_protocols TLSv1.2 TLSv1.3;
    ssl_ciphers HIGH:!aNULL:!MD5;
    
    # Redirect HTTP to HTTPS
    error_page 497 =301 https://$server_name$request_uri;
}

# Redirect HTTP traffic
server {
    listen 80;
    server_name example.com;
    return 301 https://$server_name$request_uri;
}
```

3. Configure Apache:
```apache
<VirtualHost *:443>
    ServerName example.com
    SSLEngine on
    SSLCertificateFile /path/to/cert.pem
    SSLCertificateKeyFile /path/to/key.pem
    SSLCertificateChainFile /path/to/chain.pem
</VirtualHost>

<VirtualHost *:80>
    ServerName example.com
    Redirect / https://example.com/
</VirtualHost>
```

**Verify**: All pages should redirect HTTP → HTTPS

---

### Performance Optimization (TH06, TH11, TH12)

#### Enable Gzip Compression (TH18)

**NGINX**:
```nginx
gzip on;
gzip_types text/plain text/css text/xml text/javascript 
           application/x-javascript application/xml+rss;
gzip_min_length 1000;
gzip_vary on;
```

**Apache**:
```apache
<IfModule mod_deflate.c>
    AddOutputFilterByType DEFLATE text/html text/plain text/xml text/css
    AddOutputFilterByType DEFLATE application/javascript application/x-javascript
</IfModule>
```

#### Optimize Images (TH19)

**Modern Formats**:
```html
<picture>
    <source srcset="image.webp" type="image/webp">
    <source srcset="image.jpg" type="image/jpeg">
    <img src="image.jpg" alt="description" loading="lazy">
</picture>
```

**Resize & Compress**:
```bash
# Using ImageMagick
convert large.jpg -resize 1024x768 -quality 85 optimized.jpg

# Using cwebp
cwebp -q 80 image.jpg -o image.webp
```

#### Enable Caching (TH17)

**Browser Caching - NGINX**:
```nginx
location ~* \.(jpg|jpeg|png|gif|ico|css|js|woff|woff2)$ {
    expires 365d;
    add_header Cache-Control "public, immutable";
}

location / {
    expires 1d;
    add_header Cache-Control "public, must-revalidate";
}
```

**Browser Caching - Apache**:
```apache
<FilesMatch "\.(jpg|jpeg|png|gif|css|js)$">
    Header set Cache-Control "max-age=31536000, public"
</FilesMatch>
```

**Server-Side Caching**:
- Redis for session/data caching
- Memcached for object caching
- HTTP caching headers

#### Use CDN (TH17)

**Cloudflare Setup**:
1. Point DNS to Cloudflare
2. Enable Page Rules → Cache Level: "Cache Everything"
3. Enable Caching for HTML (use TTL 1 hour)

**AWS CloudFront**:
```bash
aws cloudfront create-distribution --origin-domain example.com \
  --default-cache-behavior file://cache-behavior.json
```

---

### Mobile Responsiveness (TH07)

**Add Viewport Meta Tag**:
```html
<head>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
</head>
```

**CSS Media Queries**:
```css
/* Mobile First */
.container {
    width: 100%;
    padding: 1rem;
}

@media (min-width: 768px) {
    .container {
        width: 750px;
        margin: 0 auto;
    }
}

@media (min-width: 1024px) {
    .container {
        width: 960px;
    }
}
```

**Test**: Google Mobile-Friendly Test tool

---

### Structured Data (TH13)

**Add JSON-LD Schema**:
```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "Article",
  "headline": "Page Title",
  "author": {
    "@type": "Person",
    "name": "Author Name"
  },
  "datePublished": "2026-05-03",
  "image": "https://example.com/image.jpg"
}
</script>
```

**Validate**: Use [Schema.org Validator](https://validator.schema.org/)

---

### Sitemap & Robots.txt

**XML Sitemap** (robots.txt):
```
Sitemap: https://example.com/sitemap.xml
```

**robots.txt**:
```
User-agent: *
Disallow: /admin/
Disallow: /private/
Allow: /

Sitemap: https://example.com/sitemap.xml
```

---

### ads.txt Configuration

Create `/ads.txt` at domain root:
```
google.com, pub-0000000000000000, DIRECT, f08c47fec0942fa0
```

Get pub ID from AdSense account.

---

## Performance Testing & Monitoring

### Lighthouse Testing
```bash
# Install
npm install -g lighthouse

# Run audit
lighthouse https://example.com --output-path=./report.html

# Automation
lighthouse https://example.com --output-path=./reports/$(date +%Y-%m-%d).html
```

### WebPageTest Integration
```bash
curl "https://www.webpagetest.org/runtest.php?url=example.com&f=json"
```

### Monitoring Setup
```javascript
// Collect Core Web Vitals
const observer = new PerformanceObserver((list) => {
  for (const entry of list.getEntries()) {
    console.log('LCP:', entry.renderTime || entry.loadTime);
  }
});

observer.observe({entryTypes: ['largest-contentful-paint']});
```

---

## Optional Improvements

### HTTP/2 & HTTP/3
```nginx
listen 443 ssl http2;
http3 on;
```

### Preloading & Prefetching
```html
<link rel="preload" href="font.woff2" as="font" crossorigin>
<link rel="prefetch" href="next-page.html">
<link rel="dns-prefetch" href="//cdn.example.com">
```

### Service Workers
```javascript
if ('serviceWorker' in navigator) {
  navigator.serviceWorker.register('/sw.js');
}
```

---

## Common Performance Issues & Fixes

| Issue | Cause | Fix | Time |
|-------|-------|-----|------|
| LCP >2.5s | Large images, render-blocking JS | Optimize images, defer JS | 2-8h |
| CLS >0.1 | Ads/fonts causing layout shift | Use size containers, font-display | 1-4h |
| FID >100ms | Heavy JS execution | Code splitting, async JS | 2-6h |
| Slow DNS | DNS provider | Switch to faster DNS | 30m |
| No HTTPS | No SSL certificate | Get certificate, configure | 1-4h |

---

## Automation Scripts

```bash
# Performance check script
npm run perf-check

# SSL certificate renewal (auto)
certbot renew --quiet

# Cache clearing
cloudflare purge-cache

# CDN optimization
aws cloudfront create-invalidation --distribution-id XXXX --paths "/*"
```

---

## Success Metrics

- [ ] All pages HTTPS (no HTTP)
- [ ] LCP <2.5s, CLS <0.1, FID <100ms
- [ ] Mobile responsive (pass Mobile-Friendly Test)
- [ ] Sitemap and robots.txt valid
- [ ] Schema validation passing
- [ ] Compression enabled (>50% size reduction)
- [ ] CDN active for static assets
- [ ] SSL certificate valid for 12+ months

---

**Related Skills**:
- Audit results → `technical-audit`
- Verify fixes → `resubmission-readiness-check`
- Ongoing monitoring → `health-check-automation`
