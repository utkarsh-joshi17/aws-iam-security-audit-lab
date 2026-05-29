# AWS IAM Security Audit — Findings Report

**Auditor:** Utkarsh Joshi  
**Date:** 29-May-2026  
**Account Type:** AWS Free Tier  
**Tools Used:** AWS IAM Credential Report, IAM Access Analyzer  

---

## Findings Summary

| # | Finding | Severity | Status |
|---|---|---|---|
| 1 | MFA not enabled on lab-admin | HIGH | Resolved ✅ |
| 2 | Direct policy attachment on user | MEDIUM | Open |
| 3 | Weak password policy | MEDIUM | Resolved ✅ |

---

## Finding 1 — MFA Not Enabled on lab-admin

| Field | Detail |
|---|---|
| **Severity** | HIGH |
| **Affected User** | lab-admin |
| **Finding** | MFA was not enabled on lab-admin at time of audit |
| **Risk** | If password is compromised, attacker gets full AdministratorAccess with no second factor to block them |
| **MITRE ATT&CK** | T1078.004 — Valid Accounts: Cloud Accounts |
| **Fix Applied** | Enabled virtual MFA using Google Authenticator |
| **Status** | Resolved ✅ |

![MFA Enabled](../screenshots/06-lab-admin-user-summary.png)

---

## Finding 2 — Direct Policy Attachment on User

| Field | Detail |
|---|---|
| **Severity** | MEDIUM |
| **Affected User** | lab-admin |
| **Finding** | AdministratorAccess is attached directly to lab-admin user instead of through an IAM role |
| **Risk** | AWS best practice recommends permissions via roles not users. Direct attachment is harder to audit and rotate |
| **MITRE ATT&CK** | T1098.001 — Account Manipulation |
| **Fix Applied** | Not yet applied — recommended improvement |
| **Status** | Open |

![Permissions](../screenshots/09-lab-admin-permissions.png)

---

## Finding 3 — Weak Password Policy

| Field | Detail |
|---|---|
| **Severity** | MEDIUM |
| **Affected User** | All IAM users |
| **Finding** | Default AWS password policy was too weak |
| **Risk** | Users could set short simple passwords increasing brute force risk |
| **MITRE ATT&CK** | T1110 — Brute Force |
| **Fix Applied** | Set minimum 14 characters with uppercase, lowercase, numbers and symbols |
| **Status** | Resolved ✅ |

![Password Policy](../screenshots/05-password-policy-updated.png)

---

## Controls Passed

| Control | Observation | Status |
|---|---|---|
| Root MFA enabled | Root account has MFA active | PASS ✅ |
| No root access keys | Root account has no active access keys | PASS ✅ |
| No lab-admin access keys | lab-admin has no active access keys | PASS ✅ |
| Access Analyzer | Zero external access findings | PASS ✅ |
| Fresh passwords | All passwords recently set | PASS ✅ |

---

## Credential Report Analysis

![Credential Report](../screenshots/04-credential-report-csv.png)

| User | MFA | Access Keys | Last Login | Risk |
|---|---|---|---|---|
| root | ✅ Enabled | ✅ None | 29-May-2026 | Low |
| lab-admin | ✅ Enabled | ✅ None | 26-May-2026 | Low |
