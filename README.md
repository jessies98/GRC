# TeleMedica GRC Assessment & Security Awareness (SATE) Program

## Executive Summary
This repository contains a comprehensive Governance, Risk, and Compliance (GRC) assessment and remediation program designed for **TeleMedica**, a multinational telehealth provider operating in the US (California, Virginia, New York) and the UK (London), in close cross-border collaboration with sister company **MediCom GmbH** (Berlin).

The project audits TeleMedica's baseline Information Security Policy against federal, state, international, and healthcare industry standards, identifies critical compliance and architectural gaps, and establishes a targeted **Security Awareness, Training, and Education (SATE)** program to drive an enterprise-wide culture of compliance.

---

## Governance & Regulatory Alignment

TeleMedica's information security baseline was analyzed across multiple regulatory and standard frameworks:

* **NIST Cybersecurity Framework (CSF 2.0)**: Evaluated across core functions, identifying data types and establishing risk management strategies for data at rest and data in transit.
* **NIST Risk Management Framework (RMF)**: Aligned with the seven-step lifecycle, implementing continuous monitoring via the Security Operations Center (SOC).
* **NIST SP 800-53 (Rev. 5)**: Evaluated security control **AT-2 (Literacy Training and Awareness)** via TeleMedica's Learning Management System.
* **ISO/IEC 27001:2013**: Audited **Annex A.9 (Access Control)** to enforce role-based access control (RBAC), least privilege, and scheduled user entitlement reviews.
* **HIPAA Security & Breach Notification Rules**: Assessed safeguards over Protected Health Information (PHI), encryption standards in transit, and incident response structure using the **DACER** (Detect, Analyze, Contain, Eradicate, Recover) methodology.
* **GDPR (EU 2016/679)**: Audited cross-border data transfer security between US infrastructure and MediCom GmbH in Germany using IPsec VPN tunnels.
* **State Regulations (Massachusetts 201 CMR 17.00)**: Evaluated technical protections for personal information, including mandatory encrypted USB devices and automated malware scanning of removable media.

---

## Gap Analysis & Risk Register

| Risk ID | Framework / Law | Vulnerability / Deficiency | Inherent Risk | Recommended Control / Remediation |
| :--- | :--- | :--- | :--- | :--- |
| **R-01** | **HIPAA Security Rule** / **NIST SP 800-52** | TeleMedica uses deprecated **SSL 2.0** for data-in-transit across US and European endpoints. | **Critical** | Deprecate SSL 2.0; enforce **TLS 1.2 or higher** on all transport channels and web/API endpoints. |
| **R-02** | **NIST SP 800-63-3** | Access policy relies exclusively on single-factor passwords with 90-day rotations; lacks MFA. | **High** | Mandate **Multi-Factor Authentication (MFA)** using authenticator apps, FIDO2 tokens, or biometrics. |
| **R-03** | **HIPAA Retention Rules** | Current policy contains no formal data retention schedule (HIPAA requires a 6-year minimum). | **Medium** | Formulate an enterprise data retention and archival schedule mandating a 6-year record lifecycle. |
| **R-04** | **Business Continuity / DR** | Disaster Recovery policy lacks quantified Recovery Time Objectives (RTOs) for patient-facing services. | **High** | Establish defined RTO/RPO metrics and expand failover drills to the London secondary data center. |

---

## Security Awareness, Training, and Education (SATE) Program

To remediate operational deficiencies and address non-compliance risks, a tailored SATE program was architected around two core security initiatives:

### Initiative 1: Modern Transport Encryption Migration (SSL 2.0 to TLS 1.2+)
* **Audience**: IT Infrastructure and Systems Engineering teams.
* **Format**: Hands-on interactive simulation workshops mirroring cross-border data pipelines between the US and Berlin.
* **Objective**: 100% elimination of legacy SSL 2.0 and full migration to TLS 1.2+ within 6 months.
* **Success Metric**: Firewall and network log audits confirming zero active SSL 2.0 handshakes.

### Initiative 2: Enterprise Multi-Factor Authentication (MFA) Rollout
* **Audience**: All enterprise personnel, contractors, and executive leadership.
* **Format**: Digital LMS modules featuring video demonstrations, step-by-step setup guides, and practical threat awareness (password-spray, credential stuffing, phishing).
* **Objective**: 100% organization-wide MFA adoption enforced through conditional access within 30 days of training.
* **Success Metric**: Identity provider authentication logs validating that 100% of logins enforce MFA.

---

## Continuous Improvement & Feedback Mechanisms
* **Post-Workshop Surveys**: Technical attendees evaluate the clarity and effectiveness of cryptographic migration procedures to refine future engineering modules.
* **Monthly Pulse Surveys**: Distributed over a 90-day rollout window to track user confidence with MFA mechanisms, cross-referenced with IT Helpdesk ticket volume and IAM audit logs to address authentication roadblocks.
* **Biannual Access & Policy Audits**: Independent review of role assignments, privilege lifecycles, and data destruction compliance to verify adherence to NIST and ISO controls.

---

## Supporting Project Documentation
* **Baseline Policy**: [`TeleMedica Information Security Policy.docx`](./TeleMedica%20Information%20Security%20Policy.docx)
* **Policy Analysis & Legal Evaluation**: [`QEN1 Task 1.docx`](./QEN1%20Task%201.docx)
* **SATE Program Plan**: [`Task 2.docx`](./Task%202.docx)
