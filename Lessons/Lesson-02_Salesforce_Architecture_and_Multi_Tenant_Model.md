## Lesson 2 — Salesforce Architecture & Multi-Tenant Model

### Objective

By the end of this lesson you should understand:

1. What a Salesforce Org is
2. Cloud architecture
3. Multi-tenant architecture
4. Metadata-driven platform
5. Sandbox vs Production
6. Why Salesforce scales

---

### 1. What is Salesforce Architecture?

Architecture = How Salesforce works internally.

High-level:

```
Users
↓
UI (Lightning Experience)
↓
Business Logic
↓
Database
↓
Infrastructure (Cloud)
```

Unlike traditional apps:

```
Company owns servers ❌
Company manages DB ❌
Company patches infra ❌
```

Salesforce handles all that.

You configure.

---

### 2. What is an Org?

**Org (Organization)** = Your Salesforce environment.

Think:

```
Company
└── Salesforce Org
    ├── Users
    ├── Data
    ├── Security
    └── Apps
```

Example:

Your project:

```
Employee Learning System
```

That entire application lives inside one Org.

---

### 3. Multi-Tenant Architecture (Very Important)

Salesforce serves many customers using shared infrastructure.

Imagine:

```
Apartment Building
```

One building → many apartments.

Each apartment:

- Private
- Secure
- Independent

Salesforce:

```
Shared Servers
├── Company A
├── Company B
└── Company C
```

Each company:

- Separate data
- Separate users
- Separate configurations

Benefits:

- Lower cost
- Automatic upgrades
- High availability
- Easy scaling

---

### 4. Metadata-Driven Architecture

Salesforce mostly stores configuration as **metadata**.

Examples:

| Metadata | Data |
| --- | --- |
| Object | Employee records |
| Fields | Employee values |
| Validation Rule | User input |
| Flow | Process execution |

Example:

Create:

```
Course Object
```

That definition = Metadata

Create:

```
Course = Salesforce Admin
```

That entry = Data

This becomes very important later.

---

### 5. Production vs Sandbox

#### Production

Real environment.

Contains:

- Actual users
- Actual business data

#### Sandbox

Testing environment.

Used for:

- Development
- QA
- Training

Rule:

> Never experiment directly in Production.

---

### Mini Project

For our Learning System:

Environment plan:

```
Sandbox
↓
Testing
↓
Production
```

---

### Assignment

#### Q1. What is an Org?

An **Org (Organization)** in Salesforce is a dedicated environment or workspace where a company stores and manages its Salesforce data, users, applications, security settings, and configurations.

Example:\
If a company uses Salesforce to manage customers and employees, all their records, objects, reports, and settings exist inside their Salesforce Org.

---

#### Q2. Explain Multi-Tenant Architecture in your own words.

**Multi-Tenant Architecture** means multiple companies share the same Salesforce infrastructure (servers, platform, and resources), but each company's data remains completely isolated and secure.

Example:\
Think of an apartment building:

- The building = Salesforce Platform
- Apartments = Different company Orgs
- Each family uses the same building but has private rooms and belongings.

Benefits:

- Lower infrastructure cost
- Automatic updates
- High scalability
- Secure data separation

---

#### Q3. Difference between Data and Metadata?

| Data | Metadata |
| --- | --- |
| Actual information stored in Salesforce | Structure/configuration of Salesforce |
| Changes frequently | Changes less often |
| Stored as records | Stored as settings/configurations |
| Example: Employee records | Example: Custom Object, Fields |

Example:

- Employee Name = Narendra → **Data**
- Employee Object with fields → **Metadata**

---

#### Q4. Should admins directly build in Production? Why?

**No, admins should not directly build in Production.**

Reason:

1. Risk of affecting live users
2. Can introduce errors into business processes
3. Difficult to test safely
4. Best practice is to use **Sandbox → Test → Deploy to Production**

Typical flow:\
Development Sandbox → Testing → UAT → Production

---

#### Q5. You create a Custom Object called Employee. Is it Data or Metadata?

Creating a **Custom Object called Employee** is **Metadata**.

Reason:

- You are creating the structure/schema.
- The actual Employee records stored later become **Data**.

Example:

- Employee Object → Metadata ✅
- Employee Record (Narendra, DevOps Engineer) → Data ✅

**Quick Memory Trick:**\
**Structure = Metadata**\
**Stored Information = Data**

---

