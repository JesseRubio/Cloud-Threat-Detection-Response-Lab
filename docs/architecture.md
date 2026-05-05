# Architecture

## High-Level Design

The lab is designed around a realistic cloud security operations workflow:

1. **Attack Simulation**  
   Controlled activity such as suspicious IAM changes, public S3 exposure, or unusual API calls.

2. **Telemetry Collection**  
   CloudTrail records AWS API activity and delivers logs to S3.

3. **Threat Detection**  
   GuardDuty analyzes cloud telemetry and generates security findings.

4. **Event Routing**  
   EventBridge routes matching findings and events to downstream targets.

5. **Automated Response**  
   Lambda enriches alerts, creates evidence summaries, and can optionally trigger containment actions.

6. **Analyst Triage**  
   The analyst reviews evidence, validates the alert, documents root cause, and recommends remediation.
