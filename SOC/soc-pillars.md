# Security Operations Center (SOC)

> **Overview:** A Security Operations Center (SOC) is a centralized operational unit that continuously monitors an organization's digital infrastructure to detect, analyze, and respond to cybersecurity threats in real time.

```mermaid
graph LR
    SOC[<b>SOC Operations</b>]
    
    SOC --> P[<b>People</b>]
    SOC --> PR[<b>Process</b>]
    SOC --> T[<b>Technology</b>]
    
    P --> P1[Tier 1: Triage Analyst]
    P --> P2[Tier 2: Incident Responder]
    P --> P3[Tier 3: Threat Hunter]
    P --> P4[SOC Manager]
    
    PR --> PR1[Standard Operating Procedures]
    PR --> PR2[Incident Response Playbooks]
    PR --> PR3[SLA / KPIs: MTTD, MTTR]
    
    T --> T1[SIEM: Log Aggregation]
    T --> T2[EDR: Endpoint Detection]
    T --> T3[SOAR: Workflow Automation]
```
