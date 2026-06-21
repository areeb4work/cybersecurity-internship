# Cybersecurity Internship - OWASP Juice Shop Security Assessment

**Duration:** 3 Weeks | **Tool:** OWASP ZAP 2.17.0 | **App:** OWASP Juice Shop

## Overview
A 3-week hands-on cybersecurity internship performing complete
vulnerability assessment, security remediation, and advanced
security implementation on the OWASP Juice Shop — a deliberately
vulnerable Node.js web application used for security training.

---

## Week 1 - Vulnerability Assessment

### Setup Commands
```bash
git clone https://github.com/juice-shop/juice-shop.git
cd juice-shop
npm install
npm start
```

### Tools Used
- OWASP ZAP 2.17.0 - automated scanning + proxy
- Firefox Developer Tools - manual XSS and header testing
- Browser Console - API endpoint inspection

### Vulnerabilities Found - 9 Total

| # | Vulnerability | Severity | Found By |
|---|---|---|---|
| 1 | SQL Injection - Auth Bypass | Critical | Manual Testing |
| 2 | Cross-Site Scripting (XSS) | High | Manual Testing |
| 3 | Exposed Admin Config Endpoint | High | ZAP History |
| 4 | Mass User Data Exposure | High | Browser Console |
| 5 | Exposed FTP Directory | High | ZAP Spider |
| 6 | Missing CSP Headers | Medium | ZAP Active Scan |
| 7 | CORS Wildcard Misconfiguration | Medium | ZAP Alerts |
| 8 | Weak Password Policy | Medium | Manual Testing |
| 9 | Timestamp Disclosure | Low | ZAP Spider |

---

## Week 2 - Security Fixes

### Packages Installed
```bash
npm install validator bcrypt jsonwebtoken helmet
npm install --save-dev @types/bcrypt
```

### Files Modified & Fixes Applied

| File | Fix Applied | Vulnerability Addressed |
|---|---|---|
| server.ts | Helmet.js activated, CORS restricted | CSP headers, CORS wildcard |
| routes/login.ts | Email validation added | SQL Injection |
| lib/insecurity.ts | bcrypt replacing MD5 | Weak password storage |
| routes/search.ts | sanitizeHtml added | XSS in search bar |

### Verification
All fixes tested live - SQL injection blocked, XSS JavaScript
execution blocked, security headers confirmed in browser DevTools.

---

## Week 3 - Advanced Security & Logging

### Packages Installed
```bash
npm install winston
```

### What Was Implemented
- **Nmap** port scanning against localhost:3000
- **Winston** security logging added to 3 TypeScript files
- **Security checklist** - 31 best practices documented

### Files Modified for Logging

| File | Logger Events |
|---|---|
| server.ts | Server startup logged |
| routes/login.ts | Successful login, failed login, blocked attacks |
| routes/search.ts | XSS attempts detected and logged |

### Security Log Sample
---

## Repository Structure
cybersecurity-internship/
├── README.md
├── reports/
│   ├── Week1_Complete_Assessment_Report.docx
│   ├── Week2_Security_Fixes_Complete_Report.docx
│   └── Week3_Advanced_Security_Report.docx
├── code-modifications/
│   ├── server.ts
│   ├── login.ts
│   ├── search.ts
│   └── insecurity.ts
├── configuration/
│   └── package.json
└── logs/
└── security.log

---

## Key Findings Summary

| Week | Task | Outcome |
|---|---|---|
| Week 1 | Assessment | 9 vulnerabilities found including Critical SQL Injection |
| Week 2 | Fixes | 6 security fixes applied and verified |
| Week 3 | Advanced | Nmap scanning + Winston logging + 31-item checklist |

---

## Disclaimer
> All security testing was performed exclusively on a local
> instance of OWASP Juice Shop running at localhost:3000.

## Author
> Areeb Ahsan
