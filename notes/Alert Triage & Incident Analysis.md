# THM SOC Level 1 – Alert Triage & Incident Analysis

## Overview
Completed SOC Level 1 Blue Team exercises focused on alert triage,
incident classification, and escalation decision-making.
The scenarios emphasized correlation across multiple data sources
(email, firewall, proxy) and analyst judgment rather than tool usage.

## Scenarios Analyzed

### 1. Phishing Email – HR Onboarding Impersonation
- Sender domain impersonated HR onboarding services
- External link used to lure the user into credential interaction
- Classified as True Positive due to domain mismatch and social engineering

### 2. Firewall Alert – Blacklisted URL Access Attempt
- Internal endpoint attempted to access a known malicious shortened URL
- Connection was blocked by firewall
- Highlighted that “blocked” does not equal “no incident”
- Required user validation and correlation with email alerts

### 3. Phishing Email – Amazon Delivery Failure
- Brand impersonation using non-legitimate domain
- Urgency and deadline pressure
- Embedded shortened URL matched firewall-blocked indicator
- Correlated with Scenario #2 as part of the same campaign

### 4. Phishing Email – Microsoft Account Security Alert
- Look-alike domain impersonating Microsoft
- Fear-based messaging using foreign IP and location
- High risk of credential harvesting

## Key SOC Level 1 Skills Practiced
- Alert triage and prioritization
- True Positive vs False Positive classification
- Escalation decision-making
- Email + Firewall + Proxy correlation
- Identifying phishing patterns and attack chains
- Understanding SOC KPIs (MTTD, MTTA, MTTR)

## Key Takeaways
- SOC L1 is about **recognizing patterns and context**, not full remediation
- Correlation across alerts is critical to identifying attack campaigns
- Blocked activity still requires investigation
- Clear escalation reasoning is as important as technical detection

## Reflection
This exercise reinforced the importance of Blue Team fundamentals.
Understanding how phishing campaigns manifest across different logs
helps bridge defensive monitoring with attacker behavior awareness.
