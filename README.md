# cloud-support-Lab-2-S3-and-IAM-Access-Issue-Troubleshooting
## 🪣 Lab 2: AWS S3 & IAM Access Denied Contextual Analysis

This module evaluates resource policy authorization limits, IAM authentication mapping, identity enforcement boundaries, and cloud-native safety containment frameworks.

### 📋 Documented Engineering Incidents (Troubleshooting Tickets)

| Ticket Reference | Security Layer | Observed System Symptom | Applied Resolution Strategy |
| :--- | :--- | :--- | :--- |
| **[Ticket #06: Missing Identity Privileges](./lab2-aws-s3-iam/ticket-06-zero-permissions.md)** | IAM Identity Policies | API commands fail instantly via CLI endpoints, outputting a standard `AccessDenied` error. | Configured an explicit IAM user tracking profile block inside local administrative environments. |
| **[Ticket #07: Resource ARN Mismatch](./lab2-aws-s3-iam/ticket-07-wrong-resource.md)** | IAM Inline Policies | Permissions are added but queries still fail due to cross-resource path boundaries. | Restructured inline statement syntax by mapping matching target bucket resource strings. |
| **[Ticket #08: Explicit Deny Hierarchy](./lab2-aws-s3-iam/ticket-08-explicit-deny.md)** | S3 Resource Bucket Policies | Explicit identity policies are overridden completely, rejecting data visibility parameters. | Analyzed policy priorities and removed resource block parameters to restore flow patterns. |
| **[Ticket #09: Public Access Safety Block](./lab2-aws-s3-iam/ticket-09-public-containment.md)** | S3 Core Platform Guardrails | Object access modifications fail instantly with high-priority console alert notices. | Validated automatic cloud containment frameworks preventing unintentional data exposure. |
