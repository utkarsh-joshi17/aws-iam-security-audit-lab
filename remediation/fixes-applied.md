# Remediation — Fixes Applied

**Date:** 29-May-2026  
**Auditor:** Utkarsh Joshi  

---

## Fix 1 — Enabled MFA on lab-admin

**Finding:** MFA was not enabled on lab-admin  
**Severity:** HIGH  
**Steps taken:**
1. Went to IAM → Users → lab-admin
2. Clicked Security credentials tab
3. Clicked Assign MFA device
4. Selected Virtual MFA device
5. Scanned QR code using Google Authenticator
6. Entered two consecutive OTP codes to verify
7. MFA successfully enabled

**Result:** lab-admin now shows "Enabled with MFA" ✅  
**Evidence:** screenshots/06-lab-admin-user-summary.png

---

## Fix 2 — Strengthened Password Policy

**Finding:** Default password policy was too weak  
**Severity:** MEDIUM  
**Steps taken:**
1. Went to IAM → Account settings
2. Clicked Edit on Password policy
3. Set minimum length to 14 characters
4. Enabled require uppercase letters
5. Enabled require lowercase letters
6. Enabled require numbers
7. Enabled require non-alphanumeric characters
8. Saved changes

**Result:** Password policy updated successfully ✅  
**Evidence:** screenshots/05-password-policy-updated.png

---

## Fix 3 — Created IAM Access Analyzer

**Finding:** No visibility into external access to resources  
**Severity:** MEDIUM  
**Steps taken:**
1. Went to IAM → Access Analyzer
2. Clicked Create analyzer
3. Named it lab-analyzer
4. Set zone of trust to Current account
5. Analyzer created and scan completed

**Result:** Zero external access findings — account is secure ✅  
**Evidence:** screenshots/07-access-analyzer-no-findings.png

---

## Pending Fix — Direct Policy Attachment

**Finding:** AdministratorAccess attached directly to lab-admin user  
**Severity:** MEDIUM  
**Recommended fix:**
1. Create a new IAM role called AdminRole
2. Attach AdministratorAccess to the role
3. Allow lab-admin to assume the role
4. Remove direct AdministratorAccess from lab-admin user

**Status:** Pending — recommended for future implementation
