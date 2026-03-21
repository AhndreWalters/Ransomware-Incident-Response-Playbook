# Ransomware-Incident-Response-Playbook

## Overview

This repository contains a structured ransomware incident response playbook developed
for the Ministry of Education, Youth, Sports & Culture of Grenada. The playbook was
built as a direct response to a ransomware scenario involving social engineering, USB
delivery, lateral movement, and a ransom demand. It provides technical responders and
leadership teams with a clear, repeatable framework for managing and recovering from
ransomware attacks. This project was completed as the Playbook Capstone for the Cyber
Nation x Protexxa Cybersecurity Bootcamp.

## Ministry

- **Ministry:** Ministry of Education, Youth, Sports & Culture
- **Government:** Government of Grenada
- **Context:** Third capstone in a series following OSINT investigation and risk
  assessment of the same ministry

## The Scenario

A threat actor posed as a courier and delivered a malicious USB drive to the Ministry's
reception area. A staff member connected the device, executing a file named
Invoice_Request.pdf that contained zero-day ransomware. The malware exploited outdated
endpoint protection and poor network segmentation to spread laterally across ministry
systems before encrypting files and issuing a one million dollar ransom demand.

This playbook documents how the Ministry should respond if this incident occurs again.

## Objectives

- Draft clear and detailed ransomware incident response steps tied directly to the
  breach scenario.
- Create a flowchart diagram mapping the full response process with decision points
  and escalation paths.
- Identify the security tools and response teams involved at each stage.
- Document lessons learned and realistic prevention strategies to reduce future risk.

## What is a Ransomware Playbook?

A ransomware playbook is a structured document that outlines the step-by-step actions
an organization must take during a ransomware attack. Without one, incident response
becomes disorganized, decisions are delayed, and the damage grows. In a government
ministry context, the stakes are especially high because ransomware can disrupt public
services, expose citizen data, and damage institutional trust.

This playbook ensures that both technical teams and leadership know exactly what to do,
in what order, and who is responsible at every stage of the response.

## Incident Response Steps

### Triage
The first step is to identify and classify the threat quickly. This includes logging the
time and source of the initial report, notifying the cybersecurity incident response
team, disconnecting the affected system from the network, and confirming signs of
encryption or lateral movement. The incident is categorized as High severity given the
government-wide encryption and data exfiltration involved.

### Investigation
Once the threat is confirmed, the team works to understand the full scope and origin of
the attack. This involves analyzing the malicious USB and the file used as the delivery
mechanism, reviewing SIEM events and USB connection logs, tracing how the malware
moved laterally through unsegmented VLANs, and identifying any command-and-control
communication attempts.

### Containment
With the investigation underway, the priority shifts to stopping the ransomware from
spreading further. Infected devices are isolated, all USB ports are disabled
organization-wide, compromised accounts are revoked, and known malicious IPs and
domains are blocked at the firewall. Vulnerable services such as Windows SMB are
disabled to limit further spread.

### Eradication
After containment, all traces of the ransomware and the vulnerabilities it exploited
are removed. This includes running EDR and antivirus scans across all endpoints,
patching vulnerable systems, reinstalling operating systems where necessary, and
changing passwords ministry-wide.

### Recovery
Systems are restored from clean offline backups and gradually reconnected to a
segmented and monitored network. All core services including mail, DNS, and internal
databases are tested for functionality before being returned to operation. Stakeholders
are kept informed of progress throughout.

### Post-Incident Activities
The final phase focuses on institutional learning and long-term strengthening of
defenses. A formal post-incident review is conducted, cybersecurity policies are
revised, postponed training is reinstated, and the breach is reported to national
cybersecurity authorities. This playbook is updated and tested through tabletop
exercises.

## Tools and Teams

### Security Tools

| Tool | Role in Response |
|---|---|
| Endpoint Detection and Response (EDR) | Detects and isolates infected hosts during triage and eradication |
| Backup and Recovery Solutions | Restores clean system images during recovery |
| SIEM (Splunk, Azure Sentinel) | Correlates logs and detects abnormal patterns during investigation |
| USB Port Control Software | Blocks unauthorized device usage to prevent reinfection |
| Network Segmentation and VLAN Configuration | Contains lateral spread during containment and prevents future incidents |

### Response Teams

| Team | Responsibility |
|---|---|
| IT Security Team | Scanning, patching, isolation, and technical recovery |
| Incident Response Team (IRT) | Coordination, prioritization, and escalation of the response |
| Legal and Compliance | Regulatory disclosure and liability assessment |
| Communications and Public Relations | Press releases, citizen notices, and stakeholder updates |

## Lessons Learned and Prevention

**Lesson 1: Social engineering via physical delivery remains a potent threat**
Frontline staff such as receptionists must be trained to recognize suspicious behaviors
and follow proper reporting procedures before connecting any unknown device.

**Lesson 2: USB security policies were bypassed for convenience**
USB-blocking tools must be enforced consistently across all endpoints, and only
encrypted organization-issued drives should be permitted.

**Lesson 3: Poor network segmentation accelerated the spread**
VLANs and internal firewalls must be configured to isolate departments including
administration, IT, guest access, and core servers from one another.

**Lesson 4: Delayed cybersecurity training weakened staff awareness**
Quarterly security awareness programs must be mandated for all staff and treated as a
non-negotiable operational requirement.

**Lesson 5: Outdated endpoint protection left systems exposed**
Antivirus updates must be automated and EDR agent health must be monitored continuously
to ensure no endpoint is left unprotected.

**Lesson 6: Visitor access controls were not enforced**
Visitor logs, badge policies, and supervised physical access must be reinstated and
maintained consistently.

## License

This project is for academic purposes only and is not affiliated with the Government of
Grenada or the Ministry of Education, Youth, Sports & Culture. All scenarios, response
procedures, and recommendations are theoretical applications created for educational use.

<strong>[&copy; 2025 Ahndre Walters](https://github.com/AhndreWalters/Ransomware-Incident-Response-Playbook/blob/main/LICENSE) · Created as part of the Cyber Nation x Protexxa Cybersecurity Bootcamp (Cohort 1 - Grenada) · Playbook Capstone Assignment · Ministry of Education, Youth, Sports & Culture</strong>
