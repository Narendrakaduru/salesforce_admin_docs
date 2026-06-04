<h1 align="center">Salesforce Learning Via ChatGPT</h1>

Lesson 1 --- Introduction to Salesforce and CRM
=======================================================

1\. What is Salesforce?
=======================

Salesforce is a **cloud-based Customer Relationship Management (CRM) platform**.

Simple meaning:

Companies use Salesforce to manage:

-   Customers
-   Sales
-   Employees
-   Support tickets
-   Marketing
-   Business workflows
-   Reporting

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

2\. What is CRM?
================

CRM = **Customer Relationship Management**

CRM helps companies:

-   Store customer details
-   Track communication
-   Manage sales
-   Improve customer satisfaction
-   Automate business processes

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

3\. Real Business Example
=========================

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

-   Faster sales
-   Better reporting
-   Centralized data

4\. Salesforce Ecosystem
========================

Salesforce provides multiple clouds.

### Sales Cloud

Manage:

-   Leads
-   Accounts
-   Opportunities

### Service Cloud

Manage:

-   Cases
-   Support

### Experience Cloud

Customer portals

### Marketing Cloud

Marketing automation

### Commerce Cloud

Online commerce

### Platform

Custom application development

5\. Core Salesforce Concepts
============================

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

Mini Project
=============

Project:\
**Employee Learning & Certification Management System**

Requirement:

Employees should:

-   Register
-   Select skills
-   Enroll in courses
-   Track certification status

Question:

What objects might we need?

Example:

```
Employee
Course 
Enrollment
Certification
```

Hands-on Activity
=================

Create a free Salesforce Developer Org.

Go to:\
[Salesforce Developer Edition](https://developer.salesforce.com/signup?utm_source=chatgpt.com)

Steps:

1.  Sign up
2.  Login
3.  Open App Launcher
4.  Open Setup
5.  Explore homepage

Do not configure anything yet.

Knowledge Check
===============

### Q1. What does CRM stand for?

### Q2. What is Salesforce?

### Q3. Difference between Object and Record?

### Q4. Give one real-world use case of Salesforce.

### Q5. For our project, suggest at least 4 objects.

1. Customer Relationship Management

2. Salesforce is a cloud-based CRM platform used to manage customer relationships, business processes, automation, reporting, and enterprise applications.

3. 
-   **Object → Table**
-   **Record → Single entry inside the table**
-   **Field → Column**

Example:

```
Employee (Object)
ID   Name      Skill
1    Ravi      Salesforce
2    Rahul     AWS
```

Object → Employee\
Record → Employee #1

4. A company tracks customer inquiries, converts them into sales opportunities, and automates follow-ups using Salesforce.

5. Employee, Course, Enrollment, Certification

Lesson 2 --- Salesforce Architecture & Multi-Tenant Model
=======================================================

Objective
---------

By the end of this lesson you should understand:

1.  What a Salesforce Org is
2.  Cloud architecture
3.  Multi-tenant architecture
4.  Metadata-driven platform
5.  Sandbox vs Production
6.  Why Salesforce scales

1\. What is Salesforce Architecture?
------------------------------------

Architecture = How Salesforce works internally.

High-level:

```
Users 
↓
UI (Lightning Experience) 
↓
Business Logic 
↓
Database ↓Infrastructure (Cloud)
```

Unlike traditional apps:

```
Company owns servers ❌
Company manages DB ❌
Company patches infra ❌
```

Salesforce handles all that.

You configure.

2\. What is an Org?
-------------------

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

3\. Multi-Tenant Architecture (Very Important)
----------------------------------------------

Salesforce serves many customers using shared infrastructure.

Imagine:

```
Apartment Building
```

One building → many apartments.

Each apartment:

-   Private
-   Secure
-   Independent

Salesforce:

```
Shared Servers 
├── Company A 
├── Company B 
└── Company C
```

Each company:

-   Separate data
-   Separate users
-   Separate configurations

Benefits:

-   Lower cost
-   Automatic upgrades
-   High availability
-   Easy scaling

4\. Metadata-Driven Architecture
--------------------------------

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

5\. Production vs Sandbox
-------------------------

### Production

Real environment.

Contains:

-   Actual users
-   Actual business data

### Sandbox

Testing environment.

Used for:

-   Development
-   QA
-   Training

Rule:

> Never experiment directly in Production.

Mini Project Thinking
=====================

For our Learning System:

Environment plan:

```
Sandbox 
↓
Testing 
↓
Production
```

Assignment
==========

Answer these:

### Q1. What is an Org?

### Q2. Explain Multi-Tenant Architecture in your own words.

### Q3. Difference between Data and Metadata?

### Q4. Should admins directly build in Production? Why?

### Q5. Example:\ You create a Custom Object called Employee. Is it Data or Metadata?

----------------------------------------------

### Q1. What is an Org?

An **Org (Organization)** in Salesforce is a dedicated environment or workspace where a company stores and manages its Salesforce data, users, applications, security settings, and configurations.

Example:\
If a company uses Salesforce to manage customers and employees, all their records, objects, reports, and settings exist inside their Salesforce Org.

* * * * *

### Q2. Explain Multi-Tenant Architecture in your own words.

**Multi-Tenant Architecture** means multiple companies share the same Salesforce infrastructure (servers, platform, and resources), but each company's data remains completely isolated and secure.

Example:\
Think of an apartment building:

-   The building = Salesforce Platform
-   Apartments = Different company Orgs
-   Each family uses the same building but has private rooms and belongings.

Benefits:

-   Lower infrastructure cost
-   Automatic updates
-   High scalability
-   Secure data separation

* * * * *

### Q3. Difference between Data and Metadata?

| Data | Metadata |
| --- | --- |
| Actual information stored in Salesforce | Structure/configuration of Salesforce |
| Changes frequently | Changes less often |
| Stored as records | Stored as settings/configurations |
| Example: Employee records | Example: Custom Object, Fields |

Example:

-   Employee Name = Narendra → **Data**
-   Employee Object with fields → **Metadata**

* * * * *

### Q4. Should admins directly build in Production? Why?

**No, admins should not directly build in Production.**

Reason:

1.  Risk of affecting live users
2.  Can introduce errors into business processes
3.  Difficult to test safely
4.  Best practice is to use **Sandbox → Test → Deploy to Production**

Typical flow:\
Development Sandbox → Testing → UAT → Production

* * * * *

### Q5. Example: You create a Custom Object called Employee. Is it Data or Metadata?

Creating a **Custom Object called Employee** is **Metadata**.

Reason:

-   You are creating the structure/schema.
-   The actual Employee records stored later become **Data**.

Example:

-   Employee Object → Metadata ✅
-   Employee Record (Narendra, DevOps Engineer) → Data ✅

**Quick Memory Trick:**\
**Structure = Metadata**\
**Stored Information = Data**

Lesson 3 --- Salesforce Navigation & Setup
========================================

Objective
---------

By the end of this lesson you will understand:

1.  Lightning Experience
2.  App Launcher
3.  Setup Menu
4.  Object Manager
5.  Tabs and Apps
6.  Search in Setup
7.  Admin daily workflow

1\. What is Lightning Experience?
---------------------------------

Lightning Experience is Salesforce's modern UI.

Think:

```
Browser
↓
Salesforce UI
↓
Apps → Objects → Records
```

This is where Admins spend most of their time.

Main areas:

```
Navigation Bar
App Launcher
Setup
Global Search
User Profile
```

2\. App Launcher (Very Important)
---------------------------------

App Launcher lets users switch between applications.

Example:

```
Sales App
Service App
Marketing App
Custom Apps
```

Open:

```
Top Left → Grid Icon (⋮⋮⋮)
```

Example for our project:

```
Learning Management App
```

Inside:

```
Employees
Courses
Enrollments
Certifications
```

3\. Setup Menu (Admin Home)
---------------------------

This is the Admin control center.

Open:

```
Gear Icon
↓
Setup
```

Common admin areas:

| Area | Purpose |
| --- | --- |
| Users | User management |
| Object Manager | Objects & Fields |
| Flow | Automation |
| Profiles | Security |
| Reports | Analytics |

4\. Object Manager
------------------

This is where Admins create and manage:

-   Objects
-   Fields
-   Validation Rules
-   Record Types
-   Page Layouts

Example:

```
Object Manager
↓
Employee
↓
Fields & Relationships
```

5\. Tabs vs Apps
----------------

### Tab

Shortcut to an Object.

Example:

```
Employee Tab
Course Tab
```

### App

Collection of Tabs.

Example:

```
Learning App 
├── Employees 
├── Courses 
└── Certification
```

6\. Setup Search (Your Best Friend)
-----------------------------------

Top left search inside Setup.

Examples:

Search:

```
Users
Flows
Objects
Permission Sets
```

Admins use this constantly.

### Q1. What is Lightning Experience?

**Lightning Experience** is the modern user interface of Salesforce that provides an improved, faster, and more user-friendly experience for working with Salesforce applications.

Features:

-   Modern responsive UI
-   Better navigation
-   Dashboards and reports
-   Productivity tools
-   Component-based customization

Example:\
When users log into Salesforce and see the modern dashboard layout with navigation menus and apps, they are using Lightning Experience.

* * * * *

### Q2. Difference between App and Tab?

| App | Tab |
| --- | --- |
| Collection of related tabs and features | Single navigation item to access data |
| Used to organize business processes | Used to open an object/page |
| Contains multiple tabs | Belongs inside an app |
| Example: Learning Management App | Example: Employee Tab |

Example:

-   One App → Employee, Course, Enrollment Tabs
-   Each Tab → Opens one object/page

* * * * *

### Q3. Where do admins usually configure objects and fields?

Admins usually configure objects and fields in:

**Setup → Object Manager**

Inside Object Manager, admins can:

-   Create Custom Objects
-   Create Fields
-   Manage Relationships
-   Configure Validation Rules
-   Customize Page Layouts

* * * * *

### Q4. What is App Launcher used for?

**App Launcher** is used to quickly access and switch between different Salesforce Apps and available items.

Functions:

-   Open different Apps
-   Search apps
-   Access objects and tools
-   Navigate quickly

Example:\
Switch from Sales App → Service App → Learning Management App.

* * * * *

### Q5. If you create a Learning Management App containing Employee and Course tabs, what is App and what are Tabs?

-   **Learning Management** → **App**
-   **Employee** → **Tab**
-   **Course** → **Tab**

Explanation:\
The App acts as a container, and Tabs are the navigation items inside it.

Example structure:

Learning Management (App)\
├── Employee (Tab)\
└── Course (Tab)

**Quick Memory Trick:**\
**App = Folder**\
**Tabs = Files inside the folder**

Lesson 4 --- Objects, Fields & Relationships (Core Salesforce Admin Topic)
========================================================================

This is one of the most important lessons in Salesforce.

Objective
---------

By the end of this lesson you will understand:

1.  Standard Objects
2.  Custom Objects
3.  Fields and Data Types
4.  Relationships
5.  Schema Thinking
6.  Real Project Data Model

1\. What is an Object?
======================

Object = Database Table.

Objects store records.

Example:

```
Employee
```

Records:

```
Employee
------------------
101 | Narendra
102 | Rahul
```

2\. Types of Objects
====================

Standard Object
---------------

Prebuilt by Salesforce.

Examples:

-   Account
-   Contact
-   Lead
-   Opportunity
-   Case

Example:

```
Account
↓
Amazon
Microsoft
```

* * * * *

Custom Object
-------------

Created by Admins.

Example:

```
Employee__c
Course__c
Certification__c
```

(`__c` means Custom)

3\. Fields (Columns)
====================

Fields store values.

Example:

```
Employee
---------------
Name
Email
Skill
Experience
```

* * * * *

Common Field Types
------------------

| Field Type | Example |
| --- | --- |
| Text | Narendra |
| Number | 10 |
| Email | abc@gmail.com |
| Checkbox | True |
| Date | Joining Date |
| Picklist | Beginner/Advanced |
| Formula | Auto Calculate |
| Lookup | Connect Objects |

* * * * *

Example:

```
Course
----------------
Name
Duration
Category
Price
```

4\. Relationships (Very Important)
==================================

Relationships connect Objects.

* * * * *

Lookup Relationship
-------------------

Loose connection.

Example:

```
Employee
↓
Manager
```

Delete Manager?

Employee still exists.

* * * * *

Master-Detail Relationship
--------------------------

Strong Parent → Child.

Example:

```
Course
↓
Enrollment
```

Delete Course?

Enrollment deleted automatically.

Features:

-   Inherits security
-   Supports Roll-Up Summary

Many-to-Many
------------

Implemented using Junction Object.

Example:

```
Employee↓Enrollment↓Course
```

One employee → many courses\
One course → many employees

5\. Project Design
==================

Our project:

```
Employee
↓
Enrollment
↓
Course
↓
Certification
```

Possible relationships:

| Object | Relationship |
| --- | --- |
| Employee → Enrollment | Master |
| Course → Enrollment | Master |
| Employee → Certification | Lookup |

Mini Scenario
=============

Company requirement:

> Employees can enroll into many courses.

Question:

Should you use:

-   Lookup?
-   Master Detail?
-   Junction Object?

### Requirement:

> Employees can enroll into many courses.

Interpretation:

-   One Employee → Many Courses
-   One Course → Many Employees

This is a **Many-to-Many relationship**.

### Correct Answer: **Junction Object ✅**

Why?\
Salesforce does not directly support Many-to-Many relationships between two objects.

We create:

```
Employee (Object)      
   ↑      
   |
Enrollment (Junction Object)      
   |      
   ↓
Course (Object)
```

`Enrollment` becomes the bridge between Employee and Course.

Inside Enrollment:

-   Employee → Master-Detail relationship
-   Course → Master-Detail relationship

Example:

Employee:

-   Narendra
-   Ravi

Course:

-   Salesforce Admin
-   DevOps

Enrollment Records:

| Employee | Course |
| --- | --- |
| Narendra | Salesforce Admin |
| Narendra | DevOps |
| Ravi | Salesforce Admin |

This allows:

-   One Employee → multiple Courses
-   One Course → multiple Employees

### Why not Lookup?

Lookup supports loose relationships and doesn't automatically create a true many-to-many model.

### Why not only Master-Detail?

A single Master-Detail alone creates **One-to-Many**, not Many-to-Many.

### Final Design:

-   Employee ← Master-Detail → Enrollment ← Master-Detail → Course

**Answer: Junction Object (Enrollment) using two Master-Detail relationships.**

### Q1. Difference between Standard Object and Custom Object?

| Standard Object | Custom Object |
| --- | --- |
| Prebuilt by Salesforce | Created by Admin or Developer |
| Comes with default functionality | Built based on business requirements |
| Cannot be removed | Can be customized extensively |
| Example: Account, Contact, Opportunity | Example: Employee, Course, Enrollment |

Example:

-   Customer details → Standard Object
-   Employee Management → Custom Object

* * * * *

### Q2. What is a Field?

A **Field** is a place inside an object where individual pieces of information are stored.

Think:

-   Object → Table
-   Field → Column
-   Record → Row

Example:

Employee Object:

| Employee Name | Email | Department |
| --- | --- | --- |

Here:

-   Employee Name → Field
-   Email → Field
-   Department → Field

* * * * *

### Q3. Difference between Lookup and Master-Detail?

| Lookup Relationship | Master-Detail Relationship |
| --- | --- |
| Loose relationship | Strong parent-child relationship |
| Child can exist independently | Child depends on parent |
| Separate ownership | Parent controls ownership |
| Roll-Up Summary not supported | Roll-Up Summary supported |
| Parent deletion usually doesn't affect child | Parent deletion removes child records |

Example:

-   Employee → Manager → Lookup
-   Course → Enrollment → Master-Detail

* * * * *

### Q4. What relationship supports Roll-Up Summary?

✅ **Master-Detail Relationship**

Reason:\
Roll-Up Summary fields calculate values from child records.

Examples:

-   Count enrollments
-   Sum total course hours
-   Maximum score
-   Minimum price

Lookup relationships do not support Roll-Up Summary directly.

* * * * *

### Q5. Employee can enroll into many courses and one course has many employees. Which relationship design would you choose and why?

✅ **Junction Object (Many-to-Many Relationship)**

Design:

```
Employee   
   ↑
Master-Detail   
   |
Enrollment (Junction Object)   
   |
Master-Detail   
   ↓
Course
```

Why:

-   One Employee → Many Courses
-   One Course → Many Employees
-   Salesforce supports this using a Junction Object with **two Master-Detail relationships**.

Example:

| Employee | Course |
| --- | --- |
| Narendra | Salesforce Admin |
| Narendra | DevOps |
| Ravi | Salesforce Admin |

This design also allows Roll-Up Summaries and strong relationship control.

**Quick Memory Trick:**

-   Lookup → Flexible
-   Master-Detail → Parent controls Child
-   Many-to-Many → Junction Object + 2 Master-Details ✅

