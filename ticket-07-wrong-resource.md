# Ticket #07: IAM Privilege Isolation via Resource ARN String Mismatch

## 🚨 Customer Incident Report
- **Symptom:** Core storage automation engines continue to register full access block errors despite an inline data policy attachment update.
- **Behavior:** Remote runtime infrastructure queries continue to drop out with standard `AccessDenied` flags.

## 🔍 Engineering Triage & Diagnostics
1. **Policy Audit:** Reviewed the newly attached inline IAM document structure named `S3-Access-Policy` within the global identity dashboard layer.
2. **Syntax Isolation:** Confirmed the policy document correctly permits active operations (`s3:ListBucket`), but flagged a mismatch within the resource scope declaration blocks.

## 🛠️ Root Cause Analysis (RCA) & Resolution
- **Root Cause:** The inline privilege code block contained an explicit hardcoded target pointing to an incorrect placeholder entry (`arn:aws:s3:::wrong-dummy-bucket-name-here`), rendering the policy useless for the operational environment.
- **Applied Fix:** Rewrote the JSON configuration parameter matrix to correctly align with the production structural asset identifier string: `arn:aws:s3:::cloud-support-lab2-bucket-pringlejones`.

## ✅ Fix Verification
Re-evaluating terminal commands post-update confirmed immediate operational data tracking recovery, returning a clean runtime code flow.

### 🖼️ Diagnostic Evidence
**Figure 7.1: PowerShell Execution Terminating Successfully with Error-Free Return Lines**
![IAM Resource Fix Verification]<img width="1113" height="607" alt="case2-iam-fixed" src="https://github.com/user-attachments/assets/831d18b5-d17f-4bcc-8852-812001667417" />


