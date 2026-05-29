# AWS IAM Security Audit Lab

![AWS](https://img.shields.io/badge/AWS-IAM-orange)
![Status](https://img.shields.io/badge/Status-Completed-green)
![Type](https://img.shields.io/badge/Type-Security%20Audit-blue)

## Overview
This project is a hands-on AWS IAM security audit conducted using 
AWS native tools. It simulates a real-world cloud security audit 
where I identified misconfigurations, documented findings with 
severity ratings, and applied remediations.

---

## Tools Used
- AWS IAM Console
- AWS IAM Credential Report
- AWS IAM Access Analyzer
- AWS IAM Password Policy
- MITRE ATT&CK Framework

---

## Findings Summary

| # | Finding | Severity | Status |
|---|---|---|---|
| 1 | MFA not enabled on lab-admin | HIGH | Resolved ✅ |
| 2 | Direct policy attachment on user | MEDIUM | Open |
| 3 | Weak password policy | MEDIUM | Resolved ✅ |

---

## What I Did
- Created IAM users and configured console access
- Downloaded and analyzed the IAM Credential Report
- Identified security misconfigurations
- Documented findings with severity ratings and MITRE ATT&CK mappings
- Strengthened password policy to 14 character minimum
- Enabled MFA on lab-admin user
- Created IAM Access Analyzer to detect external access issues
- Documented full audit report

---

## Project Structure
aws-iam-security-audit-lab/
├── audit-findings/
│   └── findings-report.md
├── screenshots/
│   └── (10 evidence screenshots)
├── remediation/
│   └── fixes-applied.md
└── IAM_Security_Audit_Report.docx
```

---

## Skills Demonstrated
- AWS IAM administration
- Cloud security auditing
- Credential report analysis
- MITRE ATT&CK framework mapping
- Security documentation and reporting
- Misconfiguration detection and remediation

---

## Key Learnings
- MFA should be enabled on all IAM users immediately after creation
- Permissions should always be assigned through roles not directly to users
- IAM Credential Report is a powerful free tool for auditing user security
- IAM Access Analyzer helps detect unintended external access to resources
- A strong password policy is a basic but critical security control

---

## Disclaimer
This project was conducted in a personal AWS free tier account
for educational purposes only.
