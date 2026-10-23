# Ticket #08: Resource Policy Privilege Precedence Conflict (Explicit Deny Overrides Allow)

## 🚨 Customer Incident Report
- **Symptom:** Automated programmatic access keys are suddenly blocked from retrieving target directory tree objects.
- **Behavior:** The API returns structural `AccessDenied` failures despite zero changes occurring at the user identity policy layer.

## 🔍 Engineering Triage & Diagnostics
1. **IAM Verification:** Validated that user-level configurations remain open and completely unchanged.
2. **Resource Perimeter Evaluation:** Triage shifted directly onto the target data container layer, reviewing explicit access control matrix entries.

## 🛠️ Root Cause Analysis (RCA) & Resolution
- **Root Cause:** A high-priority resource-level **S3 Bucket Policy** statement was injected containing a explicit `"Effect": "Deny"` property value, instantly superseding and nullifying the user's IAM "Allow" parameters.
- **Applied Fix:** Purged the overriding resource policy logic statement entirely from the cloud storage container parameters.

## ✅ Fix Verification
Removing the bucket boundary override instantly restored full read/write communication capabilities to the administrative proxy.

### 🖼️ Diagnostic Evidence
**Figure 8.1: AWS S3 Resource Policy Editor Showcasing the Contesting Deny Code Structure**
![S3 Explicit Deny Configuration]<img width="1440" height="860" alt="case3-explicit-deny" src="https://github.com/user-attachments/assets/5353af64-67e4-45d5-ab52-87cf2bdfcbac" />


