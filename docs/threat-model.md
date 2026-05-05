# Threat Model

## Assets

- AWS account
- IAM users, roles, and policies
- S3 buckets
- CloudTrail logs
- GuardDuty findings
- Lambda response functions

## Threat Scenarios

| Threat | Risk | Detection |
|---|---|---|
| Root account usage | Full account compromise | CloudTrail root login detection |
| MFA disabled | Reduced account protection | DeactivateMFADevice event |
| Public S3 exposure | Data leakage | S3 policy / ACL change detection |
| Unusual region activity | Attacker staging activity | Region allowlist detection |
| GuardDuty high severity finding | Active threat behavior | EventBridge finding rule |

## Response Goals

- Preserve evidence
- Enrich alerts
- Reduce manual triage
- Document incident context
- Recommend remediation
