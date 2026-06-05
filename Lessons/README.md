<h1 align="center">Salesforce Admin Learning — Lesson Index</h1>

> All lessons are organized in a **logical learning order** for progressive understanding.
> Each lesson builds on the concepts from the previous one.

---

## Learning Path

| # | Lesson | Topic Area | File |
|---|--------|-----------|------|
| 01 | Introduction to Salesforce and CRM | Foundation | [Lesson-01](./Lesson-01_Introduction_to_Salesforce_and_CRM.md) |
| 02 | Salesforce Architecture & Multi-Tenant Model | Foundation | [Lesson-02](./Lesson-02_Salesforce_Architecture_and_Multi_Tenant_Model.md) |
| 03 | Salesforce Navigation & Setup | Foundation | [Lesson-03](./Lesson-03_Salesforce_Navigation_and_Setup.md) |
| 04 | Objects, Fields & Relationships | Data Model | [Lesson-04](./Lesson-04_Objects_Fields_and_Relationships.md) |
| 05 | Create Objects & Fields (Hands-On) | Data Model | [Lesson-05](./Lesson-05_Create_Objects_and_Fields_Hands_On.md) |
| 06 | Formula Fields & Roll-Up Summary | Data Model | [Lesson-06](./Lesson-06_Formula_Fields_and_Roll_Up_Summary.md) |
| 07 | Validation Rules | Data Model | [Lesson-07](./Lesson-07_Validation_Rules.md) |
| 08 | Salesforce Security Model | Security | [Lesson-08](./Lesson-08_Salesforce_Security_Model.md) |
| 09 | User Management, Licenses & Access | Security | [Lesson-09](./Lesson-09_User_Management_Licenses_and_Access.md) |
| 10 | Advanced Security Operations | Security | [Lesson-10](./Lesson-10_Advanced_Security_Operations.md) |
| 11 | Salesforce Flow Builder | Automation | [Lesson-11](./Lesson-11_Salesforce_Flow_Builder.md) |
| 12 | Approval Processes | Automation | [Lesson-12](./Lesson-12_Approval_Processes.md) |
| 13 | Reports & Dashboards | Analytics | [Lesson-13](./Lesson-13_Reports_and_Dashboards.md) |
| 14 | Sales Cloud & Service Cloud | Cloud Products | [Lesson-14](./Lesson-14_Sales_Cloud_and_Service_Cloud.md) |
| 15 | UI & Productivity | Customization | [Lesson-15](./Lesson-15_UI_and_Productivity.md) |
| 16 | Data Management | Data Ops | [Lesson-16](./Lesson-16_Data_Management.md) |
| 17 | Deployment, Sandbox & Change Sets | Release Mgmt | [Lesson-17](./Lesson-17_Deployment_Sandbox_and_Change_Sets.md) |
| 18 | Salesforce DevOps Basics | DevOps | [Lesson-18](./Lesson-18_Salesforce_DevOps_Basics.md) |

---

## Topic Areas

### Foundation (Lessons 1–3)
Start here. Understand what Salesforce is, how it works under the hood, and how to navigate the UI.

- **Lesson 01** — What is Salesforce? What is CRM? Real business use cases.
- **Lesson 02** — Multi-tenant architecture, metadata model, Salesforce Orgs.
- **Lesson 03** — Lightning UI, App Launcher, Setup Menu, Object Manager.

---

### Data Model (Lessons 4–7)
Learn how data is structured in Salesforce — objects, fields, relationships, formulas, and validation.

- **Lesson 04** — Standard vs Custom Objects, field types, relationship types.
- **Lesson 05** — Hands-on: Create custom objects and fields in your Org.
- **Lesson 06** — Formula fields and Roll-Up Summary fields.
- **Lesson 07** — Validation rules to enforce data quality.

---

### Security (Lessons 8–10)
Master Salesforce's layered security model — who can see what, and why.

- **Lesson 08** — Profiles, Roles, OWD, Sharing Rules — the full security stack.
- **Lesson 09** — User management, license types, permission sets, access control.
- **Lesson 10** — Advanced security: field-level security, record access, audit trails.

---

### Automation (Lessons 11–12)
Automate business processes using Flow and Approval Processes.

- **Lesson 11** — Flow Builder: Record-triggered, screen flows, scheduled flows.
- **Lesson 12** — Approval processes for multi-step business approvals.

---

### Analytics (Lesson 13)
Turn your data into insights.

- **Lesson 13** — Reports, dashboards, report types, charts, and filters.

---

### Cloud Products (Lesson 14)
Understand Salesforce's core cloud offerings.

- **Lesson 14** — Sales Cloud (leads, opportunities, forecasting) and Service Cloud (cases, knowledge, omni-channel).

---

### Customization (Lesson 15)
Customize the Salesforce UI for your users.

- **Lesson 15** — Lightning App Builder, page layouts, list views, compact layouts.

---

### Data Ops (Lesson 16)
Import, export, and maintain clean data.

- **Lesson 16** — Data Loader, Import Wizard, data quality, deduplication.

---

### Release Management & DevOps (Lessons 17–18)
Deploy changes safely and build a DevOps pipeline.

- **Lesson 17** — Sandboxes, Change Sets, deployment strategies.
- **Lesson 18** — Salesforce DX, CI/CD, version control, DevOps Center.

---

## Reordering Notes

> The following lessons were resequenced from the original document for better logical flow:

| New Order | Original Order | Reason |
|-----------|---------------|--------|
| Lesson 06 (Formula Fields) | Was Lesson 7 | Formulas must be understood before Validation Rules |
| Lesson 07 (Validation Rules) | Was Lesson 6 | Validation rules use formula syntax |
| Lesson 09 (User Management) | Was Lesson 17 | Grouped with Security domain (Lessons 8–10) |
| Lesson 10 (Advanced Security) | Was Lesson 16 | Deepens the Security domain block |
| Lesson 17 (Deployment/Sandbox) | Was Lesson 13 | Deployment precedes DevOps concepts |
