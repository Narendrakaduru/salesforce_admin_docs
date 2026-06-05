## Lesson 1 — Introduction to Salesforce and CRM

### Objective

By the end of this lesson you should understand:

1. What Salesforce is
2. What CRM is
3. Real business use cases
4. The Salesforce ecosystem
5. Core Salesforce concepts

---

### 1. What is Salesforce?

Salesforce is a **cloud-based Customer Relationship Management (CRM) platform**.

Simple meaning:

Companies use Salesforce to manage:

- Customers
- Sales
- Employees
- Support tickets
- Marketing
- Business workflows
- Reporting

Think of Salesforce as:

> ERP → manages operations\
> CRM → manages customer relationships

Salesforce stores all business data in one centralized platform.

Example:

Without Salesforce:

```
Excel
Emails
WhatsApp
Multiple tools
```

With Salesforce:

```
Customer → Lead → Opportunity → Sale → Support
```

Everything stays connected.

---

### 2. What is CRM?

CRM = **Customer Relationship Management**

CRM helps companies:

- Store customer details
- Track communication
- Manage sales
- Improve customer satisfaction
- Automate business processes

Example:

Imagine you sell cloud services.

Customer process:

```
Customer visits website
  ↓
Lead created
  ↓
Sales team contacts
  ↓
Opportunity created
  ↓
Deal won
  ↓
Support team handles issues
```

Salesforce manages this complete lifecycle.

---

### 3. Real Business Example

Company:\
**VisionsDream Cloud**

Current problems:

| Problem | Solution in Salesforce |
| --- | --- |
| Customer data in Excel | Store in Salesforce |
| Manual approvals | Approval Flow |
| No visibility | Dashboards |
| Duplicate records | Duplicate Rules |
| Email tracking issue | Automation |

Business outcome:

- Faster sales
- Better reporting
- Centralized data

---

### 4. Salesforce Ecosystem

Salesforce provides multiple clouds.

#### Sales Cloud

Manage:

- Leads
- Accounts
- Opportunities

#### Service Cloud

Manage:

- Cases
- Support

#### Experience Cloud

Customer portals

#### Marketing Cloud

Marketing automation

#### Commerce Cloud

Online commerce

#### Platform

Custom application development

---

### 5. Core Salesforce Concepts

You will hear these every day:

| Concept | Meaning |
| --- | --- |
| Org | Salesforce environment |
| Object | Database table |
| Record | Row |
| Field | Column |
| App | Collection of features |
| Report | Data analysis |
| Dashboard | Visual reports |

Example:

```
Employee Object
├── Name
├── Email
└── Skill
```

---

### Mini Project

Project:\
**Employee Learning & Certification Management System**

Requirement:

Employees should:

- Register
- Select skills
- Enroll in courses
- Track certification status

Question:

What objects might we need?

Example:

```
Employee
Course
Enrollment
Certification
```

---

### Hands-On Activity

Create a free Salesforce Developer Org.

Go to:\
[Salesforce Developer Edition](https://developer.salesforce.com/signup?utm_source=chatgpt.com)

Steps:

1. Sign up
2. Login
3. Open App Launcher
4. Open Setup
5. Explore homepage

Do not configure anything yet.

---

### Knowledge Check

#### Q1. What does CRM stand for?

Customer Relationship Management

#### Q2. What is Salesforce?

Salesforce is a cloud-based CRM platform used to manage customer relationships, business processes, automation, reporting, and enterprise applications.

#### Q3. Difference between Object and Record?

- **Object → Table**
- **Record → Single entry inside the table**
- **Field → Column**

Example:

```
Employee (Object)
ID   Name      Skill
1    Ravi      Salesforce
2    Rahul     AWS
```

Object → Employee\
Record → Employee #1

#### Q4. Give one real-world use case of Salesforce.

A company tracks customer inquiries, converts them into sales opportunities, and automates follow-ups using Salesforce.

#### Q5. For our project, suggest at least 4 objects.

Employee, Course, Enrollment, Certification

---

