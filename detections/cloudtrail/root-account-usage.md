# Detection: Root Account Usage

## Objective

Detect AWS root account activity.

## Data Source

AWS CloudTrail

## Detection Logic

Look for CloudTrail events where:

```json
"userIdentity.type": "Root"
```

## Example Query Concept

```text
eventSource = signin.amazonaws.com AND userIdentity.type = Root
```

## Severity

High

## Triage Steps

1. Confirm whether the login was expected.
2. Review source IP address and user agent.
3. Check whether MFA was used.
4. Review actions performed after login.
5. Rotate credentials if suspicious.
6. Document findings in an incident report.

## False Positives

- Planned administrative account recovery
- Initial lab setup
- Billing-only access by owner

## Remediation

- Avoid root account usage
- Enforce MFA
- Use IAM roles for admin tasks
- Monitor root activity continuously
