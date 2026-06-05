<h1 align="center">Salesforce Admin Learning Doc</h1>

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

## Lesson 3 — Salesforce Navigation & Setup

### Objective

By the end of this lesson you will understand:

1. Lightning Experience
2. App Launcher
3. Setup Menu
4. Object Manager
5. Tabs and Apps
6. Search in Setup
7. Admin daily workflow

---

### 1. What is Lightning Experience?

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

---

### 2. App Launcher (Very Important)

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

---

### 3. Setup Menu (Admin Home)

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

---

### 4. Object Manager

This is where Admins create and manage:

- Objects
- Fields
- Validation Rules
- Record Types
- Page Layouts

Example:

```
Object Manager
↓
Employee
↓
Fields & Relationships
```

---

### 5. Tabs vs Apps

#### Tab

Shortcut to an Object.

Example:

```
Employee Tab
Course Tab
```

#### App

Collection of Tabs.

Example:

```
Learning App
├── Employees
├── Courses
└── Certification
```

---

### 6. Setup Search (Your Best Friend)

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

---

### Knowledge Check

#### Q1. What is Lightning Experience?

**Lightning Experience** is the modern user interface of Salesforce that provides an improved, faster, and more user-friendly experience for working with Salesforce applications.

Features:

- Modern responsive UI
- Better navigation
- Dashboards and reports
- Productivity tools
- Component-based customization

Example:\
When users log into Salesforce and see the modern dashboard layout with navigation menus and apps, they are using Lightning Experience.

---

#### Q2. Difference between App and Tab?

| App | Tab |
| --- | --- |
| Collection of related tabs and features | Single navigation item to access data |
| Used to organize business processes | Used to open an object/page |
| Contains multiple tabs | Belongs inside an app |
| Example: Learning Management App | Example: Employee Tab |

Example:

- One App → Employee, Course, Enrollment Tabs
- Each Tab → Opens one object/page

---

#### Q3. Where do admins usually configure objects and fields?

Admins usually configure objects and fields in:

**Setup → Object Manager**

Inside Object Manager, admins can:

- Create Custom Objects
- Create Fields
- Manage Relationships
- Configure Validation Rules
- Customize Page Layouts

---

#### Q4. What is App Launcher used for?

**App Launcher** is used to quickly access and switch between different Salesforce Apps and available items.

Functions:

- Open different Apps
- Search apps
- Access objects and tools
- Navigate quickly

Example:\
Switch from Sales App → Service App → Learning Management App.

---

#### Q5. If you create a Learning Management App containing Employee and Course tabs, what is App and what are Tabs?

- **Learning Management** → **App**
- **Employee** → **Tab**
- **Course** → **Tab**

Explanation:\
The App acts as a container, and Tabs are the navigation items inside it.

Example structure:

Learning Management (App)\
├── Employee (Tab)\
└── Course (Tab)

**Quick Memory Trick:**\
**App = Folder**\
**Tabs = Files inside the folder**

---

## Lesson 4 — Objects, Fields & Relationships (Core Salesforce Admin Topic)

> This is one of the most important lessons in Salesforce.

### Objective

By the end of this lesson you will understand:

1. Standard Objects
2. Custom Objects
3. Fields and Data Types
4. Relationships
5. Schema Thinking
6. Real Project Data Model

---

### 1. What is an Object?

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

---

### 2. Types of Objects

#### Standard Object

Prebuilt by Salesforce.

Examples:

- Account
- Contact
- Lead
- Opportunity
- Case

Example:

```
Account
↓
Amazon
Microsoft
```

---

#### Custom Object

Created by Admins.

Example:

```
Employee__c
Course__c
Certification__c
```

(`__c` means Custom)

---

### 3. Fields (Columns)

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

#### Common Field Types

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

Example:

```
Course
----------------
Name
Duration
Category
Price
```

---

### 4. Relationships (Very Important)

Relationships connect Objects.

#### Lookup Relationship

Loose connection.

Example:

```
Employee
↓
Manager
```

Delete Manager?

Employee still exists.

---

#### Master-Detail Relationship

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

- Inherits security
- Supports Roll-Up Summary

---

#### Many-to-Many

Implemented using Junction Object.

Example:

```
Employee
 ↓
Enrollment
 ↓
Course
```

One employee → many courses\
One course → many employees

---

### 5. Project Design

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

---

### Mini Scenario

Company requirement:

> Employees can enroll into many courses.

Question:

Should you use:

- Lookup?
- Master Detail?
- Junction Object?

**Requirement:**

> Employees can enroll into many courses.

Interpretation:

- One Employee → Many Courses
- One Course → Many Employees

This is a **Many-to-Many relationship**.

**Correct Answer: Junction Object ✅**

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

- Employee → Master-Detail relationship
- Course → Master-Detail relationship

Example:

Employee:

- Narendra
- Ravi

Course:

- Salesforce Admin
- DevOps

Enrollment Records:

| Employee | Course |
| --- | --- |
| Narendra | Salesforce Admin |
| Narendra | DevOps |
| Ravi | Salesforce Admin |

This allows:

- One Employee → multiple Courses
- One Course → multiple Employees

**Why not Lookup?**

Lookup supports loose relationships and doesn't automatically create a true many-to-many model.

**Why not only Master-Detail?**

A single Master-Detail alone creates **One-to-Many**, not Many-to-Many.

**Final Design:**

- Employee ← Master-Detail → Enrollment ← Master-Detail → Course

**Answer: Junction Object (Enrollment) using two Master-Detail relationships.**

---

### Knowledge Check

#### Q1. Difference between Standard Object and Custom Object?

| Standard Object | Custom Object |
| --- | --- |
| Prebuilt by Salesforce | Created by Admin or Developer |
| Comes with default functionality | Built based on business requirements |
| Cannot be removed | Can be customized extensively |
| Example: Account, Contact, Opportunity | Example: Employee, Course, Enrollment |

Example:

- Customer details → Standard Object
- Employee Management → Custom Object

---

#### Q2. What is a Field?

A **Field** is a place inside an object where individual pieces of information are stored.

Think:

- Object → Table
- Field → Column
- Record → Row

Example:

Employee Object:

| Employee Name | Email | Department |
| --- | --- | --- |

Here:

- Employee Name → Field
- Email → Field
- Department → Field

---

#### Q3. Difference between Lookup and Master-Detail?

| Lookup Relationship | Master-Detail Relationship |
| --- | --- |
| Loose relationship | Strong parent-child relationship |
| Child can exist independently | Child depends on parent |
| Separate ownership | Parent controls ownership |
| Roll-Up Summary not supported | Roll-Up Summary supported |
| Parent deletion usually doesn't affect child | Parent deletion removes child records |

Example:

- Employee → Manager → Lookup
- Course → Enrollment → Master-Detail

---

#### Q4. What relationship supports Roll-Up Summary?

✅ **Master-Detail Relationship**

Reason:\
Roll-Up Summary fields calculate values from child records.

Examples:

- Count enrollments
- Sum total course hours
- Maximum score
- Minimum price

Lookup relationships do not support Roll-Up Summary directly.

---

#### Q5. Employee can enroll into many courses and one course has many employees. Which relationship design would you choose and why?

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

- One Employee → Many Courses
- One Course → Many Employees
- Salesforce supports this using a Junction Object with **two Master-Detail relationships**.

Example:

| Employee | Course |
| --- | --- |
| Narendra | Salesforce Admin |
| Narendra | DevOps |
| Ravi | Salesforce Admin |

This design also allows Roll-Up Summaries and strong relationship control.

**Quick Memory Trick:**

- Lookup → Flexible
- Master-Detail → Parent controls Child
- Many-to-Many → Junction Object + 2 Master-Details ✅

---

## Lesson 5 — Create Objects & Fields (Hands-On Admin Work)

> Now we start building.

### Objective

Create our first real Salesforce application data model.

We will create:

```
Employee__c
Course__c
Enrollment__c
```

and configure fields.

---

### Step 1 — Create Employee Object

Go:

```
Setup
  ↓
Object Manager
  ↓
Create
  ↓
Custom Object
```

Create:

| Property | Value |
| --- | --- |
| Label | Employee |
| Plural Label | Employees |
| Object Name | Employee |
| Record Name | Employee ID |
| Data Type | Auto Number |

Click:\
✔ Allow Reports\
✔ Allow Activities\
✔ Launch Tab Wizard

Save.

---

### Step 2 — Create Fields in Employee

Open:

```
Employee
 ↓
Fields & Relationships
 ↓
New
```

Create:

| Field Label | Type |
| --- | --- |
| Employee Name | Text |
| Email | Email |
| Department | Picklist |
| Experience | Number |
| Is Certified | Checkbox |

Department values:

```
DevOps
Salesforce
ServiceNow
Cybersecurity
Cloud
```

---

### Step 3 — Create Course Object

Create:

| Property | Value |
| --- | --- |
| Label | Course |
| Record Name | Course Name |

Fields:

| Field | Type |
| --- | --- |
| Duration | Number |
| Category | Picklist |
| Cost | Currency |

Category:

```
Technical
Soft Skills
Leadership
```

---

### Step 4 — Design Enrollment Object

Question only (do not create yet):

Enrollment should contain:

- Employee
- Course
- Enrollment Date
- Status

Think:\
Which fields should be:

- Master Detail?
- Date?
- Picklist?

**Answer:**

Enrollment should contain these fields:

| Field | Type |
| --- | --- |
| Employee | **Master-Detail Relationship (Employee)** |
| Course | **Master-Detail Relationship (Course)** |
| Enrollment Date | **Date** |
| Status | **Picklist** |

Suggested **Status** Picklist values:

- Enrolled
- In Progress
- Completed
- Cancelled

**Why?**

- **Employee → Master-Detail** → Each enrollment must belong to one employee.
- **Course → Master-Detail** → Each enrollment must belong to one course.
- **Enrollment Date → Date** → Stores the date of enrollment.
- **Status → Picklist** → Restricts users to predefined status values.

Relationship design:

```
Employee
  ↑
Master-Detail
  |
Enrollment
  |
Master-Detail
  ↓
Course
```

This creates a **Many-to-Many relationship**:

- One Employee → Many Courses
- One Course → Many Employees

So the **Enrollment object acts as the Junction Object**. ✅

---

### Assignment

#### Q1. Why did we use Auto Number for Employee ID?

We use **Auto Number** for Employee ID because Salesforce automatically generates a **unique identifier** for each employee record.

Benefits:

- No manual entry
- Prevents duplicate IDs
- Maintains consistent format
- Saves admin effort

Example:

```
EMP-0001
EMP-0002
EMP-0003
```

---

#### Q2. Which field type would you use for Department and why?

Use **Picklist**.

Reason:

- Restricts users to predefined values
- Maintains data consistency
- Prevents spelling mistakes and duplicates

Example values:

- DevOps
- Salesforce
- ServiceNow
- Cybersecurity
- Cloud

---

#### Q3. If Cost stores ₹ values, which field type should be used?

Use **Currency** field type.

Reason:

- Designed to store monetary values
- Supports currency formatting
- Allows calculations and reporting

Example:

```
₹5,000
₹12,500
₹25,000
```

---

#### Q4. For Enrollment object, define fields and data types.

| Field | Data Type |
| --- | --- |
| Employee | Master-Detail (Employee) |
| Course | Master-Detail (Course) |
| Enrollment Date | Date |
| Status | Picklist |

Suggested Status values:

- Enrolled
- In Progress
- Completed
- Cancelled

---

#### Q5. Which relationships should Enrollment contain?

Enrollment should contain **two Master-Detail relationships**:

1. **Enrollment → Employee (Master-Detail)**
2. **Enrollment → Course (Master-Detail)**

Reason:\
This creates a **Many-to-Many relationship** using Enrollment as the **Junction Object**.

Structure:

```
Employee
  ↑
Master-Detail
Enrollment
Master-Detail
  ↓
Course
```

This allows:

- One Employee → Multiple Courses
- One Course → Multiple Employees ✅

---

## Lesson 6 — Validation Rules (One of the Most Important Admin Skills)

> Admins use validation rules to stop bad data.

### Objective

By the end of this lesson you will know:

1. What Validation Rules are
2. Formula basics
3. Validation syntax
4. Error messages
5. Real business scenarios

---

### 1. What is a Validation Rule?

Validation Rule = Business rule that prevents invalid data from being saved.

Think:

```
User enters data
  ↓
Validation executes
  ↓
Pass → Save
Fail → Error
```

Example:

Rule:

```
Experience cannot be negative
```

Input:

```
-5
```

Result:

❌ Save blocked

---

### 2. Validation Rule Components

Every validation contains:

```
Formula
+
Error Message
+
Error Location
```

Example:

Formula:

```
Experience__c < 0
```

Message:

```
Experience cannot be negative
```

---

### 3. Common Operators

| Operator | Meaning |
| --- | --- |
| = | Equal |
| <> | Not Equal |
| > | Greater |
| < | Less |
| && | AND |
| \|\| | OR |

Functions:

| Function | Purpose |
| --- | --- |
| ISBLANK() | Empty |
| ISPICKVAL() | Picklist |
| TODAY() | Current Date |
| LEN() | Length |

---

### 4. Build Validation Rules for Our Project

#### Rule 1 — Experience Cannot Be Negative

Formula:

```
Experience__c < 0
```

Error:

```
Experience cannot be less than zero.
```

---

#### Rule 2 — Enrollment Date Cannot Be Future

Formula:

```
Enrollment_Date__c > TODAY()
```

Error:

```
Enrollment date cannot be future date.
```

---

#### Rule 3 — Certification Required

Business rule:

If Status = Completed

then Certification Required = TRUE

Assuming:

- `Status__c` → Picklist
- `Certification_Required__c` → Checkbox

Validation Rule Formula:

```
AND(ISPICKVAL(Status__c, "Completed"),NOT(Certification_Required__c))
```

Error Message:

```
Certification is required when status is Completed.
```

Error Location:

```
Field → Certification Required
```

How it works:

- Status = **Completed**
- Certification Required = **Unchecked (FALSE)**

→ ❌ Record cannot be saved

Example:

| Status | Certification Required | Result |
| --- | --- | --- |
| Completed | TRUE | ✅ Save |
| Completed | FALSE | ❌ Error |
| In Progress | FALSE | ✅ Save |

This ensures completed enrollments always have certification marked. ✅

---

### Assignment

#### Q1. What is a Validation Rule?

A **Validation Rule** is a business rule in Salesforce that prevents users from saving invalid or incorrect data.

Flow:

```
User enters data
  ↓
Validation Rule executes
  ↓
Pass → Save
Fail → Show Error
```

Example:\
Experience cannot be negative.

---

#### Q2. If Experience should not exceed 40 years, write formula logic.

Formula:

```
Experience__c > 40
```

Error Message:

```
Experience cannot exceed 40 years.
```

---

#### Q3. Which function checks Picklist values?

Use:

```
ISPICKVAL()
```

Example:

```
ISPICKVAL(Status__c, "Completed")
```

This checks whether the picklist value equals **Completed**.

---

#### Q4. Write formula logic: Enrollment Date should not be blank.

Formula:

```
ISBLANK(Enrollment_Date__c)
```

Error Message:

```
Enrollment Date is required.
```

---

#### Q5. Business Rule: If Course Cost > 0, Category cannot be blank. Formula logic:

```
AND(Cost__c > 0,ISBLANK(TEXT(Category__c)))
```

Error Message:

```
Category is required when Course Cost is greater than zero.
```

Explanation:

- `Cost__c > 0` → Course has a price
- `ISBLANK(TEXT(Category__c))` → Category is empty
- `AND()` → Both conditions true → ❌ Block save

---

## Lesson 7 — Formula Fields & Roll-Up Summary

> This is where Salesforce becomes powerful.

### Objective

By the end of this lesson:

1. Create Formula Fields
2. Understand Calculated Values
3. Use Cross-Object Formulas
4. Build Roll-Up Summary Fields
5. Use real reporting logic

---

### 1. What is a Formula Field?

Formula Field = A field whose value is automatically calculated.

No data is stored manually.

Think:

```
Input Fields
  ↓
Formula Executes
  ↓
Output Generated
```

Example:

```
Experience = 8
```

Formula:

```
Experience * 12
```

Output:

```
96 months
```

---

### 2. Formula Field Examples

#### Employee Experience in Months

Field:

```
Experience_Months__c
```

Formula:

```
Experience__c * 12
```

---

#### Certification Status

Business Rule:

If Certified → Show Completed

Formula concept:

```
IF(...)
```

Example:

```
IF(Is_Certified__c,"Completed","In Progress")
```

**How IF() works**

Structure:

```
IF(condition,value_if_true,value_if_false)
```

Meaning:

- Check a condition
- If condition = TRUE → return first value
- Otherwise → return second value

**In your example:**

```
IF(Is_Certified__c,"Completed","In Progress")
```

Breakdown:

| Part | Meaning |
| --- | --- |
| `Is_Certified__c` | Checkbox field (TRUE/FALSE) |
| `"Completed"` | Show this if checkbox = TRUE |
| `"In Progress"` | Show this if checkbox = FALSE |

---

#### Course Discount

Fields:

```
Cost__c
Discount__c
```

Formula:

```
Cost__c - (Cost__c * Discount__c / 100)
```

Business Rule:

> Calculate the final course price after applying discount.

Fields:

- `Cost__c` → Currency
- `Discount__c` → Number (Percentage)

**How it works**

Formula structure:

```
Original Cost - Discount Amount
```

Discount Amount:

```
Cost × Discount %
```

Final result:

```
Cost - Discount Amount
```

**Example:**

Course Cost:

```
₹10,000
```

Discount:

```
20
```

Calculation:

```
10000 - (10000 × 20 / 100)
```

Result:

```
₹8,000
```

---

### 3. Cross-Object Formula

Formula can reference parent fields.

Example:

```
Enrollment.Course.Cost
```

Meaning:

```
Enrollment
↓
Read Course Cost
```

Very common.

---

### 4. Roll-Up Summary (Master-Detail Only)

Roll-Up Summary calculates values from child records.

Operations:

- COUNT
- SUM
- MIN
- MAX

Example:

```
Course
↓
Enrollment
```

Count enrollments.

Output:

```
Total Enrollments = 25
```

Example:

```
Employee
↓
Enrollment
```

Roll-Up:

```
Completed Courses
```

Count child records.

---

### Real Project

Employee Dashboard:

```
Employee
├── Total Courses
├── Total Cost
└── Certification Count
```

Most of this comes from Formula + Roll-Up.

---

### Knowledge Check

#### Q1. What is a Formula Field?

A **Formula Field** is a field in Salesforce that automatically calculates and displays a value based on other fields.

Characteristics:

- Read-only
- Auto-updates when source data changes
- No manual input required

Example:

```
Cost__c - (Cost__c * Discount__c / 100)
```

---

#### Q2. Write formula: Convert Experience years into months.

Formula:

```
Experience__c * 12
```

Example:

| Experience | Output |
| --- | --- |
| 2 | 24 Months |
| 5 | 60 Months |

---

#### Q3. Write formula: If Cost > 10000 → return "Premium", else "Standard".

Formula:

```
IF(Cost__c > 10000,"Premium","Standard")
```

Example:

| Cost | Result |
| --- | --- |
| ₹15,000 | Premium |
| ₹8,000 | Standard |

---

#### Q4. Which relationship supports Roll-Up Summary and why?

✅ **Master-Detail Relationship**

Why:\
Because Salesforce allows parent records to automatically calculate values from child records.

Examples:

- Count child records
- Sum values
- Minimum value
- Maximum value

Lookup relationships do not support Roll-Up Summary directly.

---

#### Q5. Scenario: Employee has many Enrollments. Create a Roll-Up Summary requirement to show completed course count.

Design:

| Item | Answer |
| --- | --- |
| Parent Object | Employee |
| Child Object | Enrollment |
| Roll-Up Type | COUNT |
| Filter Condition | Status = Completed |

Requirement:

> Count only enrollment records where Status = Completed and display total on Employee.

Example:

Employee:

```
Narendra
```

Enrollments:

| Course | Status |
| --- | --- |
| Salesforce Admin | Completed |
| DevOps | In Progress |
| ServiceNow | Completed |

Roll-Up Result:

```
Completed Course Count = 2
```

Implementation idea:

```
Employee
 ↓
Fields & Relationships
 ↓
New
 ↓
Roll-Up Summary
 ↓
Summarized Object → Enrollment
 ↓
Roll-Up Type → COUNT
 ↓
Filter → Status = Completed
```

This automatically updates whenever enrollment status changes. ✅

---

## Lesson 8 — Salesforce Security Model

> Security is one of the most important Admin responsibilities.

### Objective

By the end of this lesson you should understand:

1. Authentication vs Authorization
2. Salesforce Security Architecture
3. Profiles
4. Permission Sets
5. Roles
6. OWD (Organization-Wide Defaults)
7. Sharing Rules
8. Field-Level Security
9. Record Access Evaluation Order
10. Real Project Security Design

---

### Why Security Matters

Imagine your company stores:

- Employee salaries
- Customer information
- Certifications
- Sales pipeline
- Internal documents

Question:

Should every user see everything?

❌ No.

Salesforce Security ensures:

```
Right User
  ↓
Right Data
  ↓
Right Time
  ↓
Right Action
```

---

### 1. Authentication vs Authorization

This confuses many beginners.

#### Authentication — Who Are You?

Verifies identity.

Example:

```
Username
Password
MFA
```

Question:

> Can user enter Salesforce?

Example:

```
narendra@company.com
+
Password
```

Access granted.

---

#### Authorization — What Can You Do?

Controls permissions.

Question:

```
Can view Employee?
Can Edit Course?
Can Delete Enrollment?
```

Example:

User logs in successfully.

But:

```
Cannot delete Course
```

That is Authorization.

---

### 2. Salesforce Security Layers (Very Important)

Security is evaluated in layers.

Think like gates.

```
Login
  ↓
Profile
  ↓
Permission Set
  ↓
Object Access
  ↓
Field Access
  ↓
Record Access
```

If blocked at any layer → access denied.

Example:

```
User logs in
  ↓
Has Employee object access
  ↓
Cannot see Salary field
  ↓
Can only view owned records
```

---

### 3. Profiles (Foundation of User Access)

Profile defines:

#### Login Access

Can user log in?

Example:

```
Allowed: 08:00 - 18:00
```

---

#### Object Permissions

CRUD:

| Permission | Meaning |
| --- | --- |
| Create | Add records |
| Read | View |
| Edit | Modify |
| Delete | Remove |

Example:

Employee:

```
Create ✓
Read ✓
Edit ✓
Delete ✗
```

---

#### Field Permissions

Controls:

```
Visible?
Editable?
```

Example:

Salary:

```
Visible ✓
Editable ✗
```

---

#### App Access

Example:

```
Learning App ✓
HR App ✗
```

Rule:

> Every user must have exactly ONE Profile.

Example:

HR Profile:

```
Employee → CRUD
Course → Read
Certification → Edit
```

---

### 4. Permission Sets (Extend Access)

Profiles should stay minimal.

Use Permission Sets for extras.

Think:

```
Profile
+
Temporary Access
```

Example:

Employee Profile:

```
Read Employee
```

Need one user to edit Course.

Add:

```
Course Editor Permission Set
```

Now:

```
Employee Profile
+
Permission Set
=
Extra access
```

Rules:

✅ Multiple allowed\
✅ Adds access\
❌ Cannot reduce access

Example:

```
Permission Set:
Course_Editor
```

Allows:

```
Edit Course
Run Reports
```

---

#### Profile vs Permission Set

| Profile | Permission Set |
| --- | --- |
| Mandatory | Optional |
| One per user | Multiple |
| Baseline access | Additional access |

---

### 5. Roles (Record Visibility)

Roles do NOT grant CRUD.

Roles decide:

> Which records users can see.

Hierarchy:

```
CEO
 ↓
Director
 ↓
Manager
 ↓
Employee
```

Example:

Manager owns:

```
Enrollment A
```

Employee owns:

```
Enrollment B
```

Manager can see subordinate records.

Employee cannot see manager records.

Example:

| User | Role |
| --- | --- |
| Narendra | Employee |
| Tarun | Manager |

Tarun sees:

```
Tarun records
+
Narendra records
```

---

#### Roles vs Profiles

| Profile | Role |
| --- | --- |
| What user can do | What records user can see |
| CRUD | Visibility |
| Mandatory | Optional |

---

### 6. Organization-Wide Defaults (OWD)

OWD defines default record access.

Think:

```
Starting Access
```

#### Private

Only owner.

Example:

```
Narendra → Enrollment
```

Only Narendra sees it.

---

#### Public Read Only

Everyone can view.

Cannot edit.

---

#### Public Read/Write

Everyone can view and edit.

Example:

Course object:

```
Public Read Only
```

Everyone sees courses.

Only admins edit.

---

### 7. Sharing Rules

Used to expand access.

Think:

```
OWD
+
Exception
```

Example:

OWD:

```
Employee = Private
```

Requirement:

HR Team must view all.

Solution:

Sharing Rule.

Types:

- Owner-based
- Criteria-based

Example:

```
Department = HR
```

Share records.

---

### 8. Field-Level Security (FLS)

Controls field access.

Example:

Employee:

```
Name
Salary
Experience
```

Employee role:

```
Salary → Hidden
```

HR role:

```
Salary → Visible
```

Controls:

- Visible
- Read Only

---

### 9. Record Access Evaluation Order (Advanced)

Salesforce checks:

```
Profile
 ↓
Permission Set
 ↓
OWD
 ↓
Role Hierarchy
 ↓
Sharing Rules
 ↓
Manual Sharing
```

Remember:

> Restrictive first → Open later

---

### 10. Real Project Security Design

Project:\
Employee Learning & Certification

Objects:

| Object | OWD |
| --- | --- |
| Employee | Private |
| Course | Public Read |
| Enrollment | Private |
| Certification | Private |

Roles:

```
CEO
 ↓
Manager
 ↓
Employee
```

Profiles:

```
Admin
Manager
Employee
```

Permission Sets:

```
Course Editor
Report Viewer
```

**Real Scenario**

Narendra logs in.

Profile:

```
Employee
```

Permissions:

```
Employee → Read
Course → Read
Enrollment → CRUD
```

Role:

```
Employee
```

OWD:

```
Private
```

Result:

```
Can create enrollment
Can see own enrollment
Cannot see others
```

---

### Hands-On Activity

Open:

```
Setup
 ↓
Profiles
 ↓
Clone Standard User
 ↓
Create Employee Profile
```

Then:

```
Setup
 ↓
Permission Sets
 ↓
Create Course Editor
```

Explore screens only.

---

### Knowledge Check

#### Q1. Explain Authentication vs Authorization.

| Authentication | Authorization |
| --- | --- |
| Verifies who the user is | Decides what the user can access |
| Happens first | Happens after login |
| Identity check | Permission check |
| Example: Username + Password | View/Edit/Delete permissions |

Example:

- Login with email + password → **Authentication**
- Access Employee records → **Authorization**

---

#### Q2. Difference between Profile and Permission Set?

| Profile | Permission Set |
| --- | --- |
| Mandatory for every user | Optional |
| Controls base access | Adds extra access |
| One user → One profile | One user → Multiple permission sets |
| Defines object, field, app permissions | Extends permissions without changing profile |

Example:

- Employee Profile → Basic access
- Course Management Permission Set → Extra course permissions

Think:

```
Profile = Base Package
Permission Set = Add-on Package
```

---

#### Q3. Difference between Role and Profile?

| Role | Profile |
| --- | --- |
| Controls record visibility | Controls actions and permissions |
| Who can see records | What users can do |
| Based on hierarchy | Based on access rights |

Example:

Profile:

```
Can Create Employee
Can Edit Enrollment
```

Role:

```
Manager can see subordinate records
```

Quick memory:

- **Profile → Actions**
- **Role → Visibility**

---

#### Q4. OWD = Private → User A owns record. User B sees it?

Answer:\
❌ **No (by default).**

If **OWD (Organization-Wide Default) = Private**:

- Only record owner
- Users above owner in role hierarchy
- Explicit sharing

can access the record.

Example:

```
User A → Owns Enrollment
User B → Cannot see
```

Unless access is granted.

---

#### Q5. Design security for the following requirement:

- Employees → see own enrollments only
- Managers → see team enrollments
- HR → see all employee records

**Profiles**

| Profile | Access |
| --- | --- |
| Employee Profile | Read/Create own enrollments |
| Manager Profile | Read team enrollments |
| HR Profile | Full employee access |

Profiles control:

- Object permissions
- Field permissions
- Apps/Tabs

**Roles**

Role Hierarchy:

```
HR
↓
Managers
↓
Employees
```

Effect:

- Managers see employee records below them
- HR sees all

**OWD**

Set:

```
Employee → Private
Enrollment → Private
```

Reason:\
Default access should be restricted.

**Sharing Rules**

Create sharing:

```
Share Employee records
From → All Employees
To → HR
Access → Read/Write
```

Optional:

```
Share Enrollment
From → Manager Role
To → Team Managers
```

Final Security Model:

| Layer | Configuration |
| --- | --- |
| Profiles | Actions |
| Roles | Visibility |
| OWD | Private |
| Sharing Rules | Exceptions |

Result:\
✅ Employees → own records only\
✅ Managers → team visibility\
✅ HR → complete employee visibility

---

## Lesson 9 — Salesforce Flow Builder

> Modern Salesforce automation is centered around Flow Builder. If you become strong in Flow, you become highly valuable as a Salesforce Admin.

### Objective

By the end of this lesson you should understand:

1. What Flow Builder is
2. Why Salesforce moved to Flow
3. Flow Architecture
4. Types of Flows
5. Flow Components
6. Record-Triggered Flow
7. Screen Flow
8. Scheduled Flow
9. Autolaunched Flow
10. Real Project Automation Design
11. Best Practices

---

### 1. What is Flow?

Flow is Salesforce's **low-code / no-code automation engine**.

It automates business processes without writing code.

Think:

```
Trigger
  ↓
Decision
  ↓
Action
  ↓
Result
```

Example:

```
Employee enrolls
  ↓
Set Status
  ↓
Send Email
  ↓
Update Employee
```

Automation completed.

---

### Why Flow?

Old Salesforce automation:

```
Workflow Rules
Process Builder
```

Modern Salesforce:

```
Flow Builder
```

Salesforce recommends Flow for nearly all new automation.

Reason:

- More powerful
- Better performance
- Supports complex logic
- Can replace multiple tools

---

### 2. Open Flow Builder

Navigate:

```
Setup
 ↓
Flow
 ↓
New Flow
```

Flow canvas appears.

This is where automation is designed.

---

### 3. Flow Architecture

Every Flow follows:

```
Start
 ↓
Get Data
 ↓
Decision
 ↓
Action
 ↓
End
```

Example:

```
Enrollment Created
 ↓
Get Employee
 ↓
Check Status
 ↓
Update Record
 ↓
Send Email
```

---

### 4. Types of Flow

#### A. Record-Triggered Flow (Most Important)

Runs automatically when records change.

Trigger:

```
Create
Update
Delete
```

No user clicks.

**Example**

Requirement:

Whenever Enrollment is created:

```
Status = Enrolled
```

Flow:

```
Enrollment Created
  ↓
Assignment
  ↓
Update Status
```

**Real Cases**

- Auto create Tasks
- Update parent records
- Send notifications
- Trigger approvals

**Before Save**

Runs before database save.

Use:

```
Fast updates
```

Example:

Auto calculate fields.

**After Save**

Runs after save.

Use:

```
Related updates
Emails
Create records
```

Example:

```
Enrollment saved
  ↓
Create Certification
```

---

#### B. Screen Flow

Shows UI screens.

User interacts.

Flow:

```
Open Screen
  ↓
Enter Values
  ↓
Submit
```

**Example**

Employee Enrollment:

```
Select Course
  ↓
Select Duration
  ↓
Submit
  ↓
Create Enrollment
```

Use Screen Flow for:

- Wizards
- Forms
- Guided setup
- Portals

---

#### C. Scheduled Flow

Runs at scheduled times.

Trigger:

```
Daily
Weekly
Monthly
```

Example:

Every day:

```
Find expired certifications
  ↓
Send reminder
```

Use Cases:

- Notifications
- Cleanup
- Reports
- Batch updates

---

#### D. Autolaunched Flow

Runs silently.

No UI.

Starts from:

- Apex
- Another Flow
- API
- Button

Example:

Certification complete:

```
Update Employee
  ↓
Send Email
  ↓
Create Log
```

---

### 5. Flow Elements (Building Blocks)

#### Start

Flow entry point.

Example:

```
Record Created
```

---

#### Get Records

Fetch data.

Example:

```
Get Employee
```

Equivalent:

```
SELECT
```

---

#### Create Records

Insert records.

Example:

```
Create Enrollment
```

Equivalent:

```
INSERT
```

---

#### Update Records

Modify records.

Example:

```
Update Certification
```

Equivalent:

```
UPDATE
```

---

#### Delete Records

Remove records.

Equivalent:

```
DELETE
```

---

#### Decision

IF / ELSE logic.

Example:

```
Score > 80
```

---

#### Assignment

Store values.

Example:

```
Status = Completed
```

---

#### Loop

Process collections.

Example:

```
Process enrollments
```

---

#### Send Email

Notify users.

Example:

```
Course Completed
```

---

### 6. Build Our Project Flow

Requirement:

When Certification Status becomes Completed:

System should:

- Update Employee
- Mark Certified
- Send Email

Flow Design:

```
Record Trigger
  ↓
Decision
  ↓
Update Employee
  ↓
Send Email
  ↓
End
```

#### Configuration

Object:

```
Certification
```

Trigger:

```
Updated
```

Condition:

```
Status = Completed
```

Actions:

```
Update Employee
Set Certified = True
Send Email
```

---

### 7. Flow Best Practices

**Keep one purpose per flow**

Good:

```
Enrollment Automation
```

Bad:

```
Everything Flow
```

**Avoid unnecessary loops**

Bad performance.

**Use Before Save for updates**

Faster.

**Add descriptions**

Document flows.

**Test in Sandbox**

Never directly in Production.

---

### Interview Questions

**What replaced Workflow Rules?**

Answer:\
Flow Builder.

---

**Difference between Before Save and After Save?**

Before:

```
Fast field updates
```

After:

```
Related records
Emails
```

---

**Which flow shows screens?**

Screen Flow.

---

### Knowledge Check

#### Q1. What is Flow?

A **Flow** is Salesforce's automation tool used to automate business processes without writing code.

Flow can:

- Create records
- Update records
- Delete records
- Send emails
- Display screens
- Make decisions
- Automate workflows

Think:

```
Trigger
  ↓
Logic
  ↓
Action
```

Example:\
Employee completes course → Update certification → Send email.

---

#### Q2. Difference between Record Triggered Flow and Screen Flow?

| Record Triggered Flow | Screen Flow |
| --- | --- |
| Runs automatically | Requires user interaction |
| Triggered by record create/update/delete | Triggered from UI |
| No user screens | Has screens/forms |
| Used for automation | Used for guided processes |

Example:

- Enrollment created → Auto update status → **Record Triggered**
- Employee registration form → **Screen Flow**

---

#### Q3. Difference between Before Save and After Save?

| Before Save | After Save |
| --- | --- |
| Runs before record is committed | Runs after record is saved |
| Faster | Slightly slower |
| Used to update same record | Used for related records, email, actions |

Example:

- Set Status automatically → Before Save
- Send Email → After Save

Memory trick:

```
Before Save → Modify
After Save → Act
```

---

#### Q4. Business Case: When Enrollment created → Set Status = Enrolled. Which Flow type?

✅ **Record Triggered Flow → Before Save**

Reason:

- Triggered automatically
- Updates same Enrollment record
- Best performance

Flow:

```
Enrollment Created
  ↓
Set Status = Enrolled
  ↓
Save
```

---

#### Q5. Design Flow: If Certification Status = Completed → Employee Is Certified = True → Send Email

**Trigger**

```
Record Triggered Flow
 ↓
Object → Certification
 ↓
Record Updated
 ↓
Decision:
Status = Completed
 ↓
Update Employee
 ↓
Send Email
 ↓
End
```

**Decision**

Decision Element:

```
Certification Status = Completed ?
```

Outcomes:

- Yes → Continue
- No → End

**Actions**

Action 1:

```
Update Records
Employee.Is_Certified = TRUE
```

Action 2:

```
Send Email
Subject: Certification Completed

Body:
Hello,

Your certification has been completed successfully.

Employee certification status has been updated.

Thank you.
```

Flow Design:

```
Start
↓
Record Triggered Flow
↓
Object: Certification
↓
Trigger:
A record is updated
↓
Condition:
Status__c = "Completed"
↓
Decision:
Certification Completed?
├── Yes
│    ↓
│  Update Records
│  Employee__r.Is_Certified__c = TRUE
│    ↓
│  Action:
│  Send Email
│    ↓
│  End
│
└── No
     ↓
    End
```

This is a standard **Record Triggered Flow + Decision + Actions** pattern in Salesforce Admin automation. ✅

---

## Lesson 10 — Approval Processes (Enterprise Automation)

> Approvals are used when records require authorization before moving forward.

### Objective

By the end of this lesson you will understand:

1. What Approval Process is
2. Approval Lifecycle
3. Approval Components
4. Entry Criteria
5. Approval Actions
6. Project Approval Design

---

### 1. What is an Approval Process?

Approval Process automates:

```
Submit
  ↓
Approve / Reject
  ↓
Execute Actions
```

Example:

Employee requests certification.

Manager approves.

System updates status.

Examples:

- Manager approval
- HR approval
- Expense approval
- Course approval

---

### 2. Approval Lifecycle

```
Draft
  ↓
Submitted
  ↓
Pending Approval
  ↓
Approved/Rejected
```

---

### 3. Components

#### Entry Criteria

Defines:

```
When approval starts
```

Example:

```
Course Cost > 50000
```

---

#### Approver

Who approves?

Example:

```
Manager
HR
Queue
Specific User
```

---

#### Approval Actions

**Initial Submission**

Example:

```
Lock Record
Send Email
```

**Final Approval**

Example:

```
Update Status
Create Certification
```

**Final Rejection**

Example:

```
Set Status = Rejected
```

---

### 4. Project Scenario

Requirement:

Employee enrolls in premium course.

Rule:

```
Cost > ₹25,000
```

Process:

```
Submit Enrollment
  ↓
Manager Approval
  ↓
HR Approval
  ↓
Approved
  ↓
Create Certification
```

---

### Knowledge Check

#### Q1. What is an Approval Process?

An **Approval Process** in Salesforce is an automation that routes records to one or more users for approval before the record can move forward.

Flow:

```
Record Submitted
  ↓
Approval Request
  ↓
Approve / Reject
  ↓
Final Action
```

Example:\
Course costing ₹30,000 requires manager approval before enrollment.

---

#### Q2. Difference between Flow and Approval Process?

| Flow | Approval Process |
| --- | --- |
| Automates business processes | Automates approvals |
| Can update/create/delete records | Focused on approve/reject |
| Supports decisions and actions | Supports approval hierarchy |
| Flexible automation | Structured approval routing |

Example:

- Auto update Enrollment → **Flow**
- Course approval workflow → **Approval Process**

---

#### Q3. What is Entry Criteria?

**Entry Criteria** defines the conditions that must be true for a record to enter the approval process.

Think:

```
Record
  ↓
Check Conditions
  ↓
Eligible → Enter Approval
```

Example:

```
Course_Cost__c > 25000
```

Only records matching this condition enter approval.

---

#### Q4. Who can act as Approver?

Approvers can be:

- Specific User
- Manager
- Role
- Queue
- Related User
- Automated Approver assignment

Example:

- Employee's Manager
- HR Manager
- Department Head

---

#### Q5. Design approval: If Course Cost > ₹25,000 → Manager approves → HR approves → Enrollment Status = Approved

**Entry Criteria**

Formula:

```
Course_Cost__c > 25000
```

**Approvers**

Step 1:

```
Approver: Employee Manager
```

Step 2:

```
Approver: HR Team / HR Manager
```

Approval Chain:

```
Manager
↓
HR
↓
Complete
```

**Actions**

Initial Submission Action:

```
Lock Record
```

Approval Step Actions:

Manager Approved:

```
Move to HR Approval
```

Final Approval Actions:

```
Update Enrollment_Status__c = "Approved"
Send Notification Email
Unlock Record
```

Flow:

```
Enrollment Submitted
↓
Entry Criteria
(Cost > ₹25,000)
↓
Manager Approval
↓
HR Approval
↓
Update Status = Approved
↓
End
```

This is a **multi-step approval process** with sequential approvals. ✅

---

## Lesson 11 — Reports & Dashboards (Business Visibility)

> Admins spend a lot of time building reports.

### Objective

By the end of this lesson:

1. Understand Reports
2. Report Types
3. Filters
4. Dashboard Components
5. Dynamic Dashboards
6. Real Project Analytics

---

### 1. What is a Report?

Report = Structured view of Salesforce data.

Used to answer:

```
What happened?
What is happening?
```

Examples:

- Employee certifications
- Course completion
- Enrollment counts

---

### 2. Report Structure

```
Object
  ↓
Filters
  ↓
Columns
  ↓
Output
```

Example:

```
Enrollment
  ↓
Status = Completed
  ↓
Show Employee
```

---

### 3. Report Types

#### Tabular

Simple list.

Example:

```
All Employees
```

---

#### Summary

Grouped report.

Example:

```
Courses grouped by Category
```

---

#### Matrix

Rows + Columns.

Example:

```
Department vs Completion
```

---

#### Joined

Multiple reports.

Example:

```
Enrollments + Certifications
```

---

### 4. Dashboard

Visual layer.

Displays:

- Charts
- Tables
- Metrics

Components:

```
Bar
Pie
Gauge
Metric
Table
```

---

### 5. Dynamic Dashboard

Runs using logged-in user access.

Example:

Manager sees:

```
Team Data
```

Employee sees:

```
Own Data
```

---

### 6. Project Dashboard

Employee Learning Dashboard:

```
Total Employees
Completed Courses
Pending Approvals
Certification Rate
```

---

### Knowledge Check

#### Q1. What is a Report?

A **Report** in Salesforce is a structured view of records used to analyze, filter, group, and summarize data.

Reports help answer questions like:

- How many employees completed training?
- Which courses have the highest enrollment?
- What is total course revenue?

Example:

```
Employee Name | Course | Status
```

Reports are data-focused.

---

#### Q2. Difference between Report and Dashboard?

| Report | Dashboard |
| --- | --- |
| Displays detailed data | Displays visual summaries |
| Table/list based | Charts and metrics |
| Source of dashboard data | Uses reports as source |
| Used for analysis | Used for monitoring |

Example:

- Report → List of enrollments
- Dashboard → Enrollment completion charts

Think:

```
Report = Data
Dashboard = Visualization
```

---

#### Q3. Difference between Summary and Matrix Report?

| Summary Report | Matrix Report |
| --- | --- |
| Groups by one field | Groups by rows and columns |
| Simpler aggregation | Multi-dimensional analysis |
| Good for totals | Good for comparisons |

Example:

Summary:

```
Department
  ↓
Employee Count
```

Matrix:

```
Department × Course Category
```

Example output:

| Department | Technical | Leadership |
| --- | --- | --- |
| DevOps | 20 | 5 |
| Salesforce | 15 | 8 |

---

#### Q4. What is Dynamic Dashboard?

A **Dynamic Dashboard** displays data according to the **logged-in user's access and permissions**.

Meaning:

- Employee sees own records
- Manager sees team records
- HR sees organization records

Example:

```
Same Dashboard
  ↓
Different View
  ↓
Based on User
```

Useful for personalized reporting.

---

#### Q5. Design dashboard for Employee Learning System

Dashboard Name:

```
Employee Learning Dashboard
```

**Components**

| Component | Type |
| --- | --- |
| Total Employees | Metric |
| Enrollment by Status | Donut Chart |
| Course Category Distribution | Pie Chart |
| Completed Courses by Department | Bar Chart |
| Monthly Enrollments | Line Chart |
| Certification Completion Rate | Gauge |

**Data Sources**

| Component | Report Source |
| --- | --- |
| Employee Summary | Employee Report |
| Enrollment Status | Enrollment Report |
| Course Analytics | Course Report |
| Certification Metrics | Enrollment + Employee Report |

**Filters**

Dashboard Filters:

| Filter | Values |
| --- | --- |
| Department | DevOps, Salesforce, Cloud |
| Course Category | Technical, Leadership |
| Enrollment Status | Enrolled, Completed |
| Date | Current Month, Quarter |

Dashboard Layout:

```
Top:
Total Employees | Completion Rate

Middle:
Enrollment Status | Course Categories

Bottom:
Monthly Trends | Department Analytics
```

This dashboard gives HR and Managers a complete learning overview in one place. ✅

---

## Lesson 12 — Sales Cloud & Service Cloud

### Objective

By the end of this lesson you will:

1. Understand Sales Cloud and Service Cloud
2. Learn how companies manage sales processes in Salesforce
3. Understand customer support workflows
4. Learn Lead → Opportunity lifecycle
5. Learn Case Management
6. Understand Queues and Assignment Rules
7. Apply these concepts to our Employee Learning System project

---

### 1. What is Sales Cloud?

Sales Cloud is Salesforce's business application used to manage the complete **sales lifecycle**, from finding potential customers to closing business deals.

Main goals:

```
Acquire Customer
↓
Build Relationship
↓
Close Deal
↓
Generate Revenue
```

Sales Cloud helps companies:

- Track customers
- Manage sales pipeline
- Increase conversion rates
- Forecast future revenue
- Automate sales activities

Typical users:

| Role | Responsibility |
| --- | --- |
| Sales Representative | Engage with customers |
| Account Executive | Close deals |
| Sales Manager | Forecast revenue |
| Leadership | Monitor business |

---

### 2. Core Sales Cloud Objects

Sales Cloud revolves around several important objects.

| Object | Purpose |
| --- | --- |
| Lead | Potential customer |
| Account | Company/Organization |
| Contact | Individual person |
| Opportunity | Sales deal |
| Task | Action item |
| Event | Meeting |

Relationship:

```
Lead
↓
Account
↓
Contact
↓
Opportunity
```

---

### 3. Lead Management

#### What is a Lead?

Lead represents someone who may become a future customer.

Lead does not mean confirmed business.

Examples:

- Website registrations
- Marketing campaigns
- Referrals
- Webinar attendees
- Manual outreach

Example:

| Field | Value |
| --- | --- |
| Name | Rahul |
| Company | ABC Corp |
| Interest | Salesforce Training |
| Source | Website |

Stored as:

```
Lead
```

---

#### Lead Lifecycle

```
New
↓
Contacted
↓
Working
↓
Qualified
↓
Converted
```

Meaning:

| Status | Meaning |
| --- | --- |
| New | Just created |
| Contacted | Initial communication |
| Working | Under evaluation |
| Qualified | Potential customer |
| Converted | Converted into business |

---

#### Lead Qualification (Very Important)

Sales teams qualify leads before investing effort.

Common method:

BANT

| Criteria | Meaning |
| --- | --- |
| Budget | Can customer afford? |
| Authority | Can they decide? |
| Need | Do they require solution? |
| Timeline | When will they buy? |

Example:

Customer says:

```
Budget Approved
Need Immediate Implementation
```

Lead becomes qualified.

---

### 4. Lead Conversion (Very Important)

Lead conversion transforms potential business into actual business records.

Conversion creates:

```
Lead
↓
Convert
↓
Account
+
Contact
+
Opportunity
```

---

Example:

Before:

| Object | Value |
| --- | --- |
| Lead | ABC Corp |

After Conversion:

| Object | Value |
| --- | --- |
| Account | ABC Corp |
| Contact | Rahul |
| Opportunity | Salesforce Training Deal |

---

#### What gets created?

##### Account

Represents company.

Example:

```
ABC Corp
```

---

##### Contact

Represents person.

Example:

```
Rahul
HR Manager
```

---

##### Opportunity

Represents deal.

Example:

```
Corporate Training
₹500000
```

---

### 5. Account Management

Account represents organization-level information.

Examples:

- Amazon
- Infosys
- Microsoft

Stores:

- Company details
- Contacts
- Opportunities
- Revenue

Relationship:

```
Account
↓
Multiple Contacts
↓
Multiple Opportunities
```

---

### 6. Contact Management

Contact represents an individual.

Example:

| Field | Example |
| --- | --- |
| Name | Rahul |
| Role | HR Manager |
| Email | rahul@abc.com |

Relationship:

```
Account
↓
Contacts
```

Example:

ABC Corp

Contacts:

```
Rahul
Priya
Amit
```

---

### 7. Opportunity Management

Opportunity represents revenue generation.

Tracks:

- Sales stages
- Amount
- Closing probability

Example:

```
Corporate Training
₹250000
```

---

#### Opportunity Lifecycle

```
Prospecting
↓
Qualification
↓
Proposal
↓
Negotiation
↓
Closed Won
OR
Closed Lost
```

---

Opportunity Fields:

| Field | Example |
| --- | --- |
| Amount | ₹250000 |
| Stage | Proposal |
| Probability | 70% |
| Close Date | 30-Jun |

---

Example:

```
ABC Corp
↓
Training Package
↓
Negotiation
↓
Closed Won
```

---

### 8. Activities (Task & Event)

Sales activities track communication.

---

#### Task

Action to complete.

Examples:

- Call customer
- Send quotation
- Follow-up

---

#### Event

Scheduled interaction.

Examples:

- Product Demo
- Client Meeting

---

Process:

```
Lead
↓
Task
↓
Meeting
↓
Opportunity
```

---

### 9. Forecasting

Forecasting predicts future revenue.

Example:

| Metric | Value |
| --- | --- |
| Sales Target | ₹2 Crores |
| Forecast | ₹1.7 Crores |

Forecast uses:

- Opportunities
- Probability
- Sales stages

Purpose:

- Planning
- Budgeting
- Performance monitoring

---

### 10. What is Service Cloud?

Service Cloud helps organizations manage support operations.

Goal:

```
Issue
↓
Resolution
↓
Customer Satisfaction
```

Teams:

- Support Agents
- Service Managers
- Escalation Teams

Core Object:

```
Case
```

---

### 11. Case Management

#### What is a Case?

Case represents support issue or request.

Examples:

- Login Issue
- Training Access Problem
- Payment Failure

---

Case Fields:

| Field | Example |
| --- | --- |
| Subject | Login Failed |
| Status | New |
| Priority | High |
| Owner | Support Queue |

---

#### Case Lifecycle

```
New
↓
Assigned
↓
Working
↓
Escalated
↓
Resolved
↓
Closed
```

---

Example:

Employee:

```
Cannot Access Course
↓
Case Created
↓
Assigned
↓
Resolved
```

---

### 12. Queues

Queue provides shared ownership.

Instead of assigning directly.

Example:

```
Training Support Queue
```

Process:

```
Case
↓
Queue
↓
Agent Picks
```

Benefits:

- Better workload management
- Faster response
- Shared responsibility

---

### 13. Assignment Rules

Assignment Rules automatically assign records.

Examples:

Case:

```
Priority = High
↓
Assign Senior Agent
```

Lead:

```
Source = Website
↓
Assign Sales Team
```

Process:

```
Record Created
↓
Evaluate Rules
↓
Assign Owner
```

---

### 14. Escalation Rules

Escalation moves unresolved work.

Example:

```
Case Open > 24 Hours
↓
Escalate
↓
Manager
```

Purpose:

- Faster resolution
- SLA compliance

---

### 15. Service Console

Service Console is a support workspace.

Contains:

- Cases
- Customer details
- Activity history
- Knowledge Articles

Benefits:

- Single workspace
- Faster issue handling

---

### Mini Project

Employee Learning System Mapping

| Salesforce Concept | Project |
| --- | --- |
| Lead | Training Request |
| Opportunity | Enrollment |
| Account | Department |
| Contact | Employee |
| Case | Learning Issue |
| Queue | HR Queue |

End-to-End:

```
Training Request
↓
Approval
↓
Enrollment
↓
Certification
↓
Support Case
↓
Resolution
```

---

### Knowledge Check

#### Q1. What is Sales Cloud?

**Sales Cloud** is a Salesforce application used to manage the complete sales process from finding potential customers to closing deals.

Main features:

- Lead Management
- Account Management
- Contact Management
- Opportunity Tracking
- Reports & Dashboards
- Sales Automation

Flow:

```
Lead
↓
Qualified
↓
Opportunity
↓
Closed Won / Lost
```

---

#### Q2. Difference between Lead and Opportunity?

| Lead | Opportunity |
| --- | --- |
| Potential customer | Qualified business deal |
| Early stage | Later sales stage |
| Limited information | Detailed sales information |
| Can be converted | Used to track revenue |

Example:

Lead:

```
Employee interested in training
```

Opportunity:

```
Employee approved for ₹30,000 training
```

Think:

- **Lead → Interest**
- **Opportunity → Revenue/Deal**

---

#### Q3. Explain Lead Conversion.

**Lead Conversion** is the process of converting a qualified lead into business records.

Typically Salesforce creates:

```
Lead
↓
Convert
↓
Account
+
Contact
+
Opportunity (optional)
```

Example:
Employee training inquiry becomes:

- Account → Company
- Contact → Employee
- Opportunity → Training purchase

Lead becomes read-only after conversion.

---

#### Q4. What is a Case?

A **Case** is a record used to track customer, employee, or support issues until resolution.

Cases help manage:

- Questions
- Complaints
- Requests
- Support tickets

Example:

```
Issue:
Unable to access training course
↓
Create Case
↓
Assign
↓
Resolve
```

---

#### Q5. Design: Employee raises a learning issue. Explain the complete flow.

**Case Lifecycle:**

```
New
↓
Assigned
↓
In Progress
↓
Waiting for Employee
↓
Resolved
↓
Closed
```

Meaning:

- New → Case created
- Assigned → Team receives
- In Progress → Investigation
- Waiting → Need employee input
- Resolved → Solution provided
- Closed → Completed

---

### Queue

Queue Name:

```
Learning Support Queue
```

Purpose:

- Holds unassigned learning cases
- Support team picks work
- Balances workload

Members:

- Training Team
- HR Support
- Learning Admin

Flow:

```
Employee
↓
Case Created
↓
Learning Queue
↓
Agent Picks
```

---

### Assignment Rule

Rule:

```
IF
Case Type = Learning Issue
THEN
Assign → Learning Support Queue
```

Additional Example:

```
Priority = High
↓
Assign → HR Manager
```

Final Design:

| Component | Configuration |
| --- | --- |
| Object | Case |
| Lifecycle | New → Assigned → Resolved |
| Queue | Learning Support |
| Assignment Rule | Auto-route learning issues |

This creates an automated support process for employee learning requests. ✅

---

## Lesson 13 — Deployment, Sandbox, Change Sets & Release Management

> Building in Salesforce is only half the job. Moving changes safely to users is equally important.

### Objective

By the end of this lesson you will:

1. Understand Salesforce environments
2. Learn Sandbox types and use cases
3. Understand deployment lifecycle
4. Learn Change Sets
5. Understand release management
6. Learn deployment best practices
7. Apply deployment concepts to our Employee Learning & Certification Management System

---

### 1. What is Deployment?

Deployment is the process of moving changes from one Salesforce environment to another.

Examples of changes:

- Objects
- Fields
- Validation Rules
- Flows
- Reports
- Profiles
- Permission Sets

Typical movement:

```
Development
↓
Testing
↓
UAT
↓
Production
```

Goal:

Move tested functionality safely.

---

### 2. Why Multiple Environments Exist

Direct production changes are risky.

Problems:

- User disruption
- Data issues
- Broken automation
- Difficult rollback

Safer approach:

```
Build
↓
Test
↓
Validate
↓
Deploy
```

Benefits:

- Controlled releases
- Better testing
- Lower production risk

---

### 3. What is Sandbox?

Sandbox is a copy of Production used for development and testing.

Purpose:

- Safe experimentation
- Development
- User testing
- Training

Rule:

Production remains protected.

Process:

```
Production
↓
Create Sandbox
↓
Build
↓
Test
↓
Deploy
```

---

### 4. Sandbox Types

Salesforce provides multiple sandbox types.

---

#### Developer Sandbox

Purpose:

Development work.

Includes:

- Metadata
- Small data storage

Use cases:

- Build objects
- Create flows
- Test automation

Example:

```
Create Employee Validation Rule
```

---

#### Developer Pro Sandbox

Purpose:

Larger development and testing.

Includes:

- Metadata
- More storage

Use cases:

- Integration testing
- Multiple feature testing

---

#### Partial Copy Sandbox

Purpose:

Testing with sample production data.

Includes:

- Metadata
- Partial production data

Use cases:

- UAT
- Business testing

Example:

```
Test Enrollment Reports
```

---

#### Full Sandbox

Purpose:

Production replica.

Includes:

- Metadata
- Full production data

Use cases:

- Performance testing
- Large testing cycles

Example:

```
Complete release testing
```

---

### 5. Sandbox Comparison

| Feature | Developer | Developer Pro | Partial | Full |
| --- | --- | --- | --- | --- |
| Metadata | Yes | Yes | Yes | Yes |
| Sample Data | No | No | Yes | Yes |
| Full Data | No | No | No | Yes |
| Development | Yes | Yes | Limited | Limited |
| UAT | No | Partial | Yes | Yes |

Selection:

```
Build
↓
Developer

User Testing
↓
Partial

Final Validation
↓
Full
```

---

### 6. Deployment Lifecycle

Typical Salesforce release flow:

```
Developer Sandbox
↓
Integration Testing
↓
UAT
↓
Production
```

Detailed flow:

```
Build
↓
Unit Test
↓
QA
↓
User Acceptance
↓
Production Release
```

Stages:

| Stage | Purpose |
| --- | --- |
| Development | Build features |
| Testing | Validate |
| UAT | Business approval |
| Production | Go live |

---

### 7. What is Change Set?

Change Set is Salesforce's deployment mechanism.

Used to move metadata.

Supports:

- Objects
- Fields
- Flows
- Validation Rules
- Reports

Does NOT move:

- Record data
- Files
- Attachments

Deployment:

```
Sandbox
↓
Outbound Change Set
↓
Upload
↓
Production
↓
Inbound Change Set
↓
Deploy
```

---

### 8. Types of Change Sets

#### Outbound Change Set

Created in source environment.

Example:

```
Developer Sandbox
↓
Upload
```

---

#### Inbound Change Set

Received in target environment.

Example:

```
Production
↓
Validate
↓
Deploy
```

---

### 9. Deploying with Change Sets

Deployment steps:

```
Create Change Set
↓
Add Components
↓
Upload
↓
Validate
↓
Deploy
```

Components:

- Objects
- Fields
- Profiles
- Flows

Best practice:

Always validate before deployment.

---

### 10. Release Management

Release Management controls how changes reach users.

Goals:

- Stable releases
- Controlled changes
- Minimal downtime

Release Cycle:

```
Requirement
↓
Development
↓
Testing
↓
Approval
↓
Production
```

Release Types:

| Type | Description |
| --- | --- |
| Major | Large feature |
| Minor | Small enhancement |
| Hotfix | Urgent fix |

---

### 11. Deployment Best Practices

Follow these rules:

- Never develop in Production
- Use Sandbox
- Validate deployments
- Backup before release
- Use naming conventions
- Test automation
- Keep release notes

Recommended process:

```
Build
↓
Peer Review
↓
Deploy
↓
Monitor
```

---

### 12. Deployment Failures & Rollback

Common reasons:

- Missing dependencies
- Validation failures
- Profile conflicts
- Flow activation errors

Recovery:

```
Failure
↓
Analyze
↓
Fix
↓
Redeploy
```

Before deployment:

- Export data
- Backup metadata

---

### Mini Project

Employee Learning & Certification Management System

Scenario:

Deploy Employee Enrollment enhancements.

Changes:

- Enrollment Object
- Validation Rules
- Approval Process
- Reports

Release Flow:

```
Developer Sandbox
↓
Build Enrollment Updates
↓
Testing Sandbox
↓
UAT Approval
↓
Production
```

Deployment Components:

| Component | Deploy |
| --- | --- |
| Objects | Yes |
| Flows | Yes |
| Reports | Yes |
| Employee Records | No |

---

### Hands-On

Perform:

1. Create Developer Sandbox
2. Open Setup
3. Navigate to Change Sets
4. Create Outbound Change Set
5. Add one Custom Object
6. Upload
7. Review deployment steps

---

### Knowledge Check

#### Q1. What is Deployment?

**Deployment** is the process of moving Salesforce changes from one environment to another.

Usually:

```
Sandbox
↓
Testing
↓
Production
```

Examples of deployed items:

- Objects
- Fields
- Validation Rules
- Flows
- Reports
- Permission changes

Goal:\
Move tested changes safely into live use.

---

#### Q2. Difference between Developer Sandbox and Full Sandbox?

| Developer Sandbox | Full Sandbox |
| --- | --- |
| Small copy of production metadata | Complete copy of production |
| Contains configuration only | Contains metadata + data |
| Used for development | Used for UAT and performance testing |
| Limited storage | Larger storage |

Example:

Developer Sandbox:

```
Build Enrollment validation rules
```

Full Sandbox:

```
Test complete Employee Learning system
```

---

#### Q3. What is Change Set?

A **Change Set** is a Salesforce deployment tool used to move metadata between related orgs.

Can deploy:

- Objects
- Fields
- Flows
- Validation Rules
- Reports
- Permission Sets

Cannot deploy:

- Record data

Flow:

```
Source Org
↓
Outbound Change Set
↓
Upload
↓
Inbound Change Set
↓
Deploy
```

---

#### Q4. Why validate before deployment?

Validation checks whether deployment will succeed **before making actual changes**.

Benefits:

- Detect missing dependencies
- Prevent deployment failures
- Reduce production risk
- Confirm tests pass

Example:

```
Validate
↓
No Errors
↓
Deploy
```

Without validation:

```
Deploy
↓
Error
↓
Rollback / Failure
```

---

#### Q5. Design deployment flow for Employee Enrollment enhancement.

Scenario:\
Deploy Enrollment enhancements:

- New fields
- Validation rules
- Flow updates
- Reports

Deployment Flow:

```
Requirement
↓
Build in Developer Sandbox
↓
Unit Testing
↓
Deploy to UAT / Full Sandbox
↓
User Acceptance Testing
↓
Create Change Set
↓
Validate Deployment
↓
Deploy to Production
↓
Post Deployment Testing
↓
Monitor
```

Deployment Components:

| Stage | Activity |
| --- | --- |
| Development | Build Enrollment enhancement |
| Testing | Verify functionality |
| UAT | Business approval |
| Change Set | Package metadata |
| Validation | Run deployment checks |
| Production | Release changes |

Example Enhancement:

```
Enrollment
+
Completed Course Rollup
+
Approval Process
+
Certification Flow
```

This follows Salesforce deployment best practices:\
**Build → Test → Validate → Deploy → Verify** ✅


## Lesson 14 — UI & Productivity

> A good Salesforce application is not only functional—it should also be easy, fast, and intuitive for users.

### Objective

By the end of this lesson you will:

1. Understand Page Layouts
2. Learn Record Types
3. Build Lightning Pages
4. Understand Dynamic Forms
5. Learn Global Actions
6. Improve user productivity
7. Apply UI design to our Employee Learning & Certification Management System

---

### 1. What is UI & Productivity in Salesforce?

UI (User Interface) determines how users interact with Salesforce.

Productivity features help users:

- Work faster
- Reduce clicks
- Improve user experience
- View relevant information
- Complete actions efficiently

Think:

```
Data
↓
Page Design
↓
User Experience
↓
Productivity
```

Salesforce provides:

- Page Layouts
- Record Types
- Lightning App Builder
- Dynamic Forms
- Global Actions

---

### 2. Page Layouts

Page Layout controls:

- Field placement
- Related lists
- Buttons
- Sections
- Visibility

Question answered:

> What does the user see on a record page?

Navigate:

```
Setup
↓
Object Manager
↓
Object
↓
Page Layouts
```

Example:

Employee Layout:

```
Employee Information
├── Name
├── Email
└── Department

Learning Information
├── Courses
└── Certifications
```

Capabilities:

- Add fields
- Remove fields
- Reorder sections
- Add buttons

Best Practices:

- Keep important fields at top
- Group related information
- Reduce scrolling

---

### 3. Record Types

Record Types allow different business processes for the same object.

Question answered:

> Should different users see different record experiences?

Example:

Object:

```
Course
```

Record Types:

```
Technical
Leadership
Compliance
```

Each Record Type can control:

- Picklist values
- Business process
- Page Layout

Example:

Technical Course:

```
Category:
Cloud
DevOps
Salesforce
```

Leadership Course:

```
Category:
Management
Communication
```

Navigation:

```
Object Manager
↓
Object
↓
Record Types
```

---

### 4. Record Type + Page Layout Relationship

Record Types and Page Layouts often work together.

Example:

```
Record Type
↓
Choose Layout
↓
Display Fields
```

Example:

Employee Role:

```
Manager
↓
Manager Layout
```

Employee Role:

```
Learner
↓
Learner Layout
```

Result:

Different UI for different users.

---

### 5. Lightning App Builder

Lightning App Builder creates pages using drag-and-drop components.

Purpose:

Build custom UI.

Navigate:

```
Setup
↓
Lightning App Builder
```

Page Types:

| Page | Purpose |
| --- | --- |
| App Page | Application pages |
| Home Page | Landing page |
| Record Page | Object records |

Example:

Employee Dashboard Page:

```
Header
├── Employee Summary
├── Certifications
└── Enrollment Metrics
```

Capabilities:

- Add components
- Rearrange sections
- Configure visibility

---

### 6. Dynamic Forms

Dynamic Forms make pages intelligent.

Question answered:

> Can Salesforce show fields only when needed?

Answer:

Yes.

Example:

If:

```
Course Type = Certification
```

Show:

```
Certification Expiry
```

Otherwise:

Hide.

Flow:

```
Condition
↓
Evaluate
↓
Show Component
```

Benefits:

- Cleaner UI
- Better experience
- Reduced clutter

Example:

Employee:

```
Certified = True
↓
Show Certification Section
```

---

### 7. Component Visibility

Control when components appear.

Rules can depend on:

- User Role
- Record Value
- Device Type
- Profile

Example:

```
Manager
↓
Show Approval Component
```

Employee:

```
Hide Approval Component
```

---

### 8. Global Actions

Global Actions allow users to perform quick actions.

Question answered:

> How can users create records faster?

Examples:

- Create Employee
- Log Activity
- Create Enrollment

Navigation:

```
Setup
↓
Global Actions
```

Example:

Click:

```
New Enrollment
```

Immediately:

```
Open Form
↓
Create Record
```

Benefits:

- Faster navigation
- Fewer clicks
- Better productivity

---

### 9. Quick Actions vs Global Actions

| Quick Action | Global Action |
| --- | --- |
| Object specific | Available globally |
| Context aware | Universal |
| Related records | Standalone |

Example:

Quick Action:

```
Create Certification
```

Global Action:

```
Create Enrollment
```

---

### 10. Mobile Productivity

Salesforce UI supports mobile optimization.

Examples:

- Compact Layout
- Dynamic Actions
- Responsive Components

Goal:

```
Desktop
+
Mobile
=
Consistent Experience
```

---

### Mini Project

Employee Learning & Certification Management System

Design:

Employee UI

```
Employee
├── Profile Section
├── Skill Section
├── Certification Section
└── Enrollment History
```

Record Types:

```
Course
├── Technical
└── Leadership
```

Dynamic Form:

```
Certified = True
↓
Show Certification Details
```

Global Action:

```
Create Enrollment
```

Lightning Page:

```
Employee Dashboard
```

---

### Hands-On

Perform:

1. Open Object Manager
2. Select Employee Object
3. Create Page Layout
4. Create Record Type
5. Open Lightning App Builder
6. Create Record Page
7. Add Dynamic Visibility

---

### Interview Questions

#### Q1. Difference between Page Layout and Record Type?

Answer:\
Page Layout controls UI layout, whereas Record Type controls business process variation.

---

#### Q2. Why use Dynamic Forms?

Answer:\
Show relevant fields conditionally.

---

#### Q3. When should Global Actions be used?

Answer:\
For fast record creation from anywhere in the application.

---

### Knowledge Check

#### Q1. What does Page Layout control?

A **Page Layout** controls how fields, sections, buttons, related lists, and actions appear to users on a record page.

Page Layout controls:

- Field visibility
- Field order
- Required fields
- Related lists
- Quick actions

Example:

```
Employee Page
↓
Employee Details
↓
Enrollment History
↓
Actions
```

Page Layout controls **how the page looks and behaves**.

---

#### Q2. Difference between Record Type and Page Layout?

| Record Type | Page Layout |
| --- | --- |
| Controls business process and record variations | Controls UI arrangement |
| Can show different picklist values | Controls field placement |
| Used for different user scenarios | Used for page design |

Example:

Record Types:

```
Technical Course
Leadership Course
```

Page Layout:

```
Fields shown differently for each type
```

Think:

- **Record Type → Which version**
- **Page Layout → How it looks**

---

#### Q3. What is Lightning App Builder?

**Lightning App Builder** is a drag-and-drop tool used to create and customize Lightning pages.

Used for:

- App Pages
- Home Pages
- Record Pages

Features:

- Add components
- Rearrange UI
- Configure visibility
- Build responsive layouts

Example:

```
Header
↓
Employee Details
↓
Related Courses
↓
Dashboard
```

---

#### Q4. What problem do Dynamic Forms solve?

**Dynamic Forms** solve the problem of showing too many fields to every user.

They allow:

- Show fields only when needed
- Conditional visibility
- Better page performance
- Less scrolling

Example:

Without Dynamic Forms:

```
Show all 50 fields
```

With Dynamic Forms:

```
Show Certification fields only if Certified = TRUE
```

Result:\
Cleaner and smarter UI.

---

#### Q5. Design UI for Employee Learning System

##### Page Layout

Employee Layout:

```
Employee Information
Enrollment Details
Certification Section
Related Courses
Activity History
```

Course Layout:

```
Course Details
Pricing
Approval Status
Enrollments
```

---

##### Record Types

Employee Record Types:

| Record Type |
| --- |
| Internal Employee |
| External Contractor |

Course Record Types:

| Record Type |
| --- |
| Technical |
| Leadership |
| Soft Skills |

Purpose:\
Different processes and picklists.

---

##### Dynamic Forms

Visibility Rules:

```
Show Certification Section
IF
Is_Certified = TRUE
```

```
Show Approval Details
IF
Cost > ₹25,000
```

Benefits:

- Cleaner UI
- Personalized experience

---

##### Global Actions

Create quick actions:

| Action | Purpose |
| --- | --- |
| New Enrollment | Create enrollment |
| Add Course | Create course |
| Submit Approval | Start approval |
| Raise Issue | Create support case |

Placement:

```
Global Header
↓
+ New Enrollment
+ Raise Issue
```

Final UI Design:

```
Record Type
↓
Page Layout
↓
Dynamic Forms
↓
Global Actions
↓
Better User Experience
```

This design gives employees, managers, and HR a clean and scalable Employee Learning System UI. ✅

## Lesson 15 — Data Management (Import, Export & Data Quality)

> Good automation on bad data still produces bad results. Data quality is one of the most important responsibilities of a Salesforce Admin.

### Objective

By the end of this lesson you will:

1. Understand Salesforce Data Management
2. Learn Data Import Wizard
3. Learn Data Loader
4. Understand Duplicate Rules
5. Learn Data Quality practices
6. Understand backup strategies
7. Apply data operations to our Employee Learning & Certification Management System

---

### 1. What is Data Management?

Data Management is the process of:

- Importing data
- Exporting data
- Cleaning records
- Preventing duplicates
- Maintaining data quality
- Protecting business information

Examples of Salesforce data:

- Employees
- Courses
- Enrollments
- Certifications
- Reports

Goal:

```
Collect
↓
Validate
↓
Store
↓
Maintain
↓
Analyze
```

Why it matters:

- Better reporting
- Reliable automation
- Accurate dashboards
- Better user adoption

---

### 2. Data Import Overview

Import means bringing external data into Salesforce.

Common sources:

- CSV files
- Excel spreadsheets
- HR systems
- ERP systems
- Legacy applications

Typical import process:

```
Source Data
↓
Prepare CSV
↓
Map Fields
↓
Validate
↓
Import
↓
Verify
```

Common imported objects:

| Object | Example |
| --- | --- |
| Employee | Employee list |
| Course | Course catalog |
| Enrollment | Learning registrations |
| Certification | Existing certifications |

---

### 3. Data Import Wizard

Data Import Wizard is Salesforce's browser-based import tool.

Best for:

- Small and medium imports
- Admin-friendly uploads
- Simple updates

Navigation:

```
Setup
↓
Data Import Wizard
```

Supports:

| Feature | Supported |
| --- | --- |
| Insert | Yes |
| Update | Yes |
| Delete | No |
| Duplicate Detection | Yes |

Advantages:

- Easy to use
- No installation
- Guided mapping

Limitations:

- Less control
- Limited volume

Example:

Import Employees.

CSV:

```
Employee Name,Email,Department
Narendra,user1@example.com,Salesforce
Rahul,user2@example.com,DevOps
```

---

### 4. Data Loader

Data Loader is Salesforce's advanced bulk data tool.

Used for:

- Large imports
- Updates
- Exports
- Deletes
- Migration

Process:

```
Open Data Loader
↓
Select Operation
↓
Upload CSV
↓
Map Fields
↓
Execute
```

Operations:

| Operation | Supported |
| --- | --- |
| Insert | Yes |
| Update | Yes |
| Upsert | Yes |
| Export | Yes |
| Delete | Yes |
| Hard Delete | Yes |

---

### 5. Import Wizard vs Data Loader

| Feature | Import Wizard | Data Loader |
| --- | --- | --- |
| Interface | Browser | Application |
| Volume | Small | Large |
| Export | No | Yes |
| Delete | No | Yes |
| Complexity | Simple | Advanced |

Selection:

```
Simple Import
↓
Import Wizard

Migration
↓
Data Loader
```

---

### 6. What is Upsert?

Upsert means:

```
Update
+
Insert
```

Behavior:

```
Record Exists
↓
Update

Record Missing
↓
Insert
```

Used with:

- External IDs
- Integrations
- Synchronization

Example:

Employee already exists:

Update.

Employee not found:

Create.

---

### 7. Duplicate Rules

Duplicate Rules prevent duplicate records.

Question answered:

> How do we stop users from creating repeated records?

Example:

```
Same Email
↓
Duplicate Found
↓
Block Save
```

Two related concepts:

---

#### Matching Rule

Defines how duplicates are detected.

Examples:

- Email
- Employee ID
- Name

---

#### Duplicate Rule

Defines what action happens.

Actions:

- Allow
- Alert
- Block

Example:

```
Email Match
↓
Show Warning
```

---

### 8. Data Quality

Data Quality means maintaining accurate records.

Problems:

- Missing values
- Duplicates
- Invalid formats
- Outdated records

Improve quality using:

- Validation Rules
- Required Fields
- Picklists
- Duplicate Rules

Process:

```
Enter
↓
Validate
↓
Store
↓
Monitor
```

Good Data:

```
Consistent
Accurate
Complete
```

---

### 9. Data Cleanup

Admins regularly clean data.

Methods:

- Merge duplicates
- Remove invalid records
- Standardize values
- Archive old data

Example:

Bad:

```
DevOpsdevopsDEVOPS
```

Good:

```
DevOps
```

---

### 10. Exporting Data

Export means extracting Salesforce records.

Reasons:

- Backup
- Reporting
- Migration
- Recovery

Process:

```
Salesforce
↓
Select Objects
↓
Generate Export
↓
Download
```

Export Types:

| Type | Description |
| --- | --- |
| Manual | One-time |
| Scheduled | Automatic |

---

### 11. Backup Strategies

Admins should never rely on production alone.

Backup before:

- Deployments
- Bulk updates
- Cleanup
- Migration

Recommended strategy:

```
Export
↓
Store Securely
↓
Version Backup
```

Backup Checklist:

- Employee
- Course
- Enrollment
- Certification

---

### 12. Import Error Handling

Import results:

```
Import
├── Success
└── Failed Records
```

Common failures:

| Error | Cause |
| --- | --- |
| Required Field Missing | Empty value |
| Duplicate Found | Duplicate Rule |
| Invalid Picklist | Wrong value |

Recovery:

```
Review Errors
↓
Fix CSV
↓
Retry
```

---

### Mini Project

Employee Learning & Certification Management System

Scenario:

Import employees into Employee object.

CSV:

```
Employee Name,Email,Department,Experience
Narendra,user1@example.com,Salesforce,4
Rahul,user2@example.com,DevOps,5
Priya,user3@example.com,Cloud,6
```

Process:

```
Prepare CSV
↓
Import Wizard
↓
Map Fields
↓
Validate
↓
Employee Created
```

Duplicate Prevention:

```
Email
↓
Matching Rule
↓
Duplicate Rule
↓
Block Duplicate
```

Backup Plan:

```
Weekly Export
↓
Secure Storage
```

---

### Hands-On

Perform:

1. Create Employee CSV
2. Open Data Import Wizard
3. Import Employee records
4. Verify records
5. Configure Duplicate Rule
6. Export Employee data

---

### Interview Questions

#### Q1. Difference between Import Wizard and Data Loader?

Answer:\
Import Wizard is simpler and browser-based, whereas Data Loader is an advanced application that supports larger volumes and bulk operations.

---

#### Q2. What is Upsert?

Answer:\
Upsert matches incoming records against existing ones; it updates existing records and inserts new ones.

---

#### Q3. Why use Duplicate Rules?

Answer:\
To prevent duplicate records from being created, ensuring data cleanliness and quality.

---

### Knowledge Check

#### Q1. What is Data Management?

**Data Management** is the process of importing, exporting, updating, cleaning, maintaining, and protecting data inside Salesforce.

Common activities:

- Import records
- Export records
- Update records
- Delete records
- Prevent duplicates
- Maintain data quality

Example:

```
CSV
↓
Import
↓
Validate
↓
Store in Salesforce
```

---

#### Q2. Difference between Import Wizard and Data Loader?

| Data Import Wizard | Data Loader |
| --- | --- |
| Browser-based | Desktop/client tool |
| Easy for admins | More powerful |
| Supports standard import operations | Supports Insert, Update, Upsert, Export, Delete |
| Smaller datasets | Large datasets |

Example:

- Import 500 employees → Import Wizard
- Import 100,000 employees → Data Loader

---

#### Q3. What is Upsert?

**Upsert = Update + Insert**

Salesforce checks whether a record already exists:

- Exists → Update
- Doesn't exist → Insert

Usually uses:

- Record ID
- External ID

Example:

CSV:

| Employee ID | Name |
| --- | --- |
| EMP001 | Narendra |
| EMP002 | Ravi |

Result:

- EMP001 exists → Update
- EMP002 missing → Create

Flow:

```
Match
↓
Update OR Insert
```

---

#### Q4. What is the difference between Matching Rule and Duplicate Rule?

| Matching Rule | Duplicate Rule |
| --- | --- |
| Defines how duplicates are identified | Defines what action happens |
| Comparison logic | Prevention logic |
| Runs behind the scenes | Blocks or warns users |

Example:

Matching Rule:

```
Email = Exact Match
```

Duplicate Rule:

```
Block save if duplicate found
```

Think:

```
Matching Rule → Detect
↓
Duplicate Rule → Act
```

---

#### Q5. Design a safe employee import process

Requirement:\
Import employees safely with duplicate prevention.

##### Step 1 — Prepare CSV

Example:

| Employee ID | Name | Email | Department |
| --- | --- | --- | --- |

Rules:

- Clean formatting
- Mandatory columns
- Unique Employee IDs

---

##### Step 2 — Import Tool

Recommended:

```
Data Import Wizard
```

For large files:

```
Data Loader
```

Operation:

```
Upsert
```

Reason:\
Avoid duplicate employee creation.

---

##### Step 3 — Duplicate Prevention

Configure:

Matching Rule:

```
Email Exact Match
Employee ID Exact Match
```

Duplicate Rule:

```
Block duplicate creation
Show warning
```

Flow:

```
Import
↓
Check Duplicate
↓
Allow / Reject
```

---

##### Step 4 — Target Backup Strategy

Before import:

```
Export Existing Employees
↓
CSV Backup
↓
Store Securely
```

After import:

- Verify counts
- Run reports
- Validate sample records

Complete Process:

```
Backup
↓
Prepare CSV
↓
Configure Matching Rule
↓
Enable Duplicate Rule
↓
Import (Upsert)
↓
Validate
↓
Audit
```

This gives a **safe, recoverable, duplicate-controlled employee import process** in Salesforce. ✅

---

## Lesson 16 — Advanced Security Operations

> Good security is not only about restricting access. It is about giving the right access to the right user at the right time.

### Objective

By the end of this lesson you will:

1. Understand Manual Sharing
2. Learn Restriction Rules
3. Understand Permission Set Groups
4. Learn Login Access Policies
5. Troubleshoot access issues
6. Apply least privilege principles
7. Apply advanced security to our Employee Learning & Certification Management System

---

### 1. What is Advanced Security Operations?

In Lesson 8, we designed security.

Now we focus on operating and maintaining security.

Question answered:

> How do admins manage changing access requirements safely?

Areas covered:

- Temporary access
- Visibility reduction
- Permission grouping
- Login controls
- Troubleshooting

Flow:

```
Design Access
↓
Assign Access
↓
Monitor
↓
Troubleshoot
↓
Improve
```

---

### 2. Manual Sharing

#### What is Manual Sharing?

Manual Sharing allows a user to share a specific record with another user without changing overall security configuration.

Question answered:

> Can I share only one record?

Answer:

Yes.

Process:

```
Record
↓
Share
↓
Select User
↓
Grant Access
```

Example:

Employee:

Narendra

Shares:

```
Enrollment Record
↓
Manager
↓
Read Only
```

Use Cases:

- Temporary collaboration
- Manager review
- Exception-based access

Characteristics:

| Feature | Manual Sharing |
| --- | --- |
| Scope | Single Record |
| Permanent | Usually No |
| Admin Required | Not always |

Important:

Manual Sharing does not change:

- OWD
- Role Hierarchy
- Profile

It affects only one record.

---

### 3. Restriction Rules

#### What are Restriction Rules?

Restriction Rules reduce record visibility.

Question answered:

> Can Salesforce hide records even after access is granted?

Answer:

Yes.

Process:

```
Visible Records
↓
Apply Restriction
↓
Filtered Records
```

Example:

User normally sees:

```
All Courses
```

Restriction:

```
Department = Salesforce
```

Result:

```
Only Salesforce Courses
```

Use Cases:

- Contractors
- Regional access
- Sensitive records
- Compliance requirements

Example:

| User | Restriction |
| --- | --- |
| Contractor | Active Certifications Only |
| Employee | Own Department Only |

---

### 4. Permission Set Groups

#### What is Permission Set Group?

Permission Set Group combines multiple Permission Sets.

Question answered:

> Can we assign multiple permissions together?

Answer:

Yes.

Process:

```
Permission Set A
+
Permission Set B
+
Permission Set C
↓
Permission Set Group
```

Example:

Learning Admin needs:

- Course Access
- Enrollment Access
- Reports Access

Group:

```
Learning_Admin_Group
```

Benefits:

- Easier administration
- Faster onboarding
- Reduced maintenance

Example:

| Permission Set | Access |
| --- | --- |
| Course Manager | Course Access |
| Enrollment Manager | Enrollment |
| Report Viewer | Reports |

↓

Permission Set Group

---

### 5. Login Access Policies

Login controls secure user access.

Question answered:

> Who can login and when?

Controls:

- Login Hours
- Login IP Range
- Session Timeout

Example:

Login Hours:

```
09:00
↓
18:00
```

Login IP:

```
Office Network
↓
Allow Access
```

Session:

```
Inactive
↓
Logout
```

Example Policies:

| Setting | Example |
| --- | --- |
| Login Hours | Office Hours |
| IP Range | Corporate Network |
| Session Timeout | 30 Minutes |

Benefits:

- Reduced unauthorized access
- Better compliance

---

### 6. Login As User

Admins sometimes troubleshoot by logging in as users.

Question answered:

> How can admins reproduce user problems?

Process:

```
Admin
↓
Login As User
↓
View Experience
```

Use Cases:

- Missing access
- UI problems
- Flow failures

Best Practice:

Use only when necessary.

---

### 7. Security Troubleshooting Framework

Common complaint:

```
I cannot see records
```

Admin checklist:

```
User
↓
Profile
↓
Permission Set
↓
Role
↓
OWD
↓
Restriction Rule
↓
Result
```

Questions:

- Object access?
- Field access?
- Record access?
- Login restrictions?

---

### 8. Least Privilege Principle

Principle:

Users receive minimum required access.

Bad:

```
Everyone = Admin
```

Good:

```
Start Small
↓
Add Required Access
```

Benefits:

- Lower risk
- Better auditing
- Easier maintenance

Example:

Employee:

```
Read
Create
```

Manager:

```
Read
Edit
```

Admin:

```
Full Access
```

---

### 9. Security Operations Lifecycle

Security is continuous.

Lifecycle:

```
Request Access
↓
Approve
↓
Assign
↓
Monitor
↓
Review
↓
Remove
```

Questions:

- Who requested?
- Why needed?
- When remove?

---

### 10. Access Governance

Governance ensures permissions remain correct.

Examples:

- Quarterly access review
- Remove inactive users
- Audit Permission Sets

Checklist:

```
Users
↓
Permissions
↓
Review
↓
Cleanup
```

---

### Mini Project

Employee Learning & Certification Management System

Requirement:

Employees:

- View own enrollments

Managers:

- Temporary review access

Contractors:

- Limited certifications

Security Design:

Manual Sharing:

```
Enrollment
↓
Share
↓
Manager
```

Restriction Rule:

```
Contractor
↓
Active Certifications Only
```

Permission Set Group:

```
Reports
+
Enrollment
+
Courses
↓
Learning_Admin_Group
```

Login Policy:

```
Office Hours
↓
Allow Login
```

Result:

```
Controlled
↓
Secure
↓
Scalable
```

---

### Hands-On

Perform:

1. Create Permission Set
2. Create Permission Set Group
3. Configure Login Hours
4. Configure Restriction Rule
5. Share one record manually
6. Verify access

---

### Interview Questions

#### Q1. What is Manual Sharing?

Answer:\
Share individual records manually.

---

#### Q2. Difference between Permission Set and Permission Set Group?

Answer:\
Permission Set Group combines multiple Permission Sets.

---

#### Q3. Why use Restriction Rules?

Answer:\
Reduce visibility.

---

### Knowledge Check

#### Q1. What is Manual Sharing?

**Manual Sharing** allows a record owner or authorized user to manually give access to a specific record to another user.

Purpose:

- Share one record without changing organization-wide access.

Example:

```
Employee A Enrollment
↓
Share
↓
Manager
↓
Read Access
```

Use case:\
Employee shares one learning request with HR.

---

#### Q2. What problem do Restriction Rules solve?

**Restriction Rules** reduce record visibility even when users already have access.

Think:

```
Access Granted
↓
Restriction Rule Applied
↓
Only allowed records visible
```

Purpose:

- Enforce additional record filtering
- Support least-privilege access

Example:

Manager can see team enrollments but only:

```
Department = Salesforce
```

Result:\
Manager sees fewer records.

---

#### Q3. What is Permission Set Group?

A **Permission Set Group** combines multiple permission sets into one assignment.

Benefits:

- Easier administration
- Reusable access bundles
- Reduces manual assignment

Example:

Permission Sets:

```
Enrollment Access
+
Course Access
+
Reporting Access
```

Combined into:

```
Learning Operations PSG
```

Assign one group instead of multiple permission sets.

---

#### Q4. What controls Login Access?

Login access is controlled using:

- Profile Login Hours
- Profile IP Ranges
- Session Settings
- MFA
- Login Access Policies

Example:

```
Login Hours: 9 AM - 8 PM
```

Example:

```
Allow office network only
```

Purpose:\
Protect Salesforce access.

---

#### Q5. Design advanced security for Employee Learning System

Requirement:\
Secure employee learning records.

##### Manual Sharing

Configuration:

```
Employee Enrollment
↓
Owner can manually share
↓
Manager / HR
```

Use:\
Temporary access for approvals.

---

##### Restriction Rules

Rule:

```
Managers
↓
Can view only
Department = Their Department
```

Example:

Manager:

```
Department = DevOps
```

Visible:\
Only DevOps enrollments.

---

##### Permission Set Groups

Create groups:

| Permission Set Group | Includes |
| --- | --- |
| Employee Learning Access | Enrollment + Course View |
| Manager Learning Access | Reports + Approval |
| HR Learning Admin | Full Employee Access |

Assignment:

```
Assign by role
```

---

##### Login Policies

Configure:

| Setting | Value |
| --- | --- |
| Login Hours | Business Hours |
| IP Range | Corporate Network |
| MFA | Enabled |
| Session Timeout | 30 mins |

---

Final Security Architecture:

```
OWD Private
↓
Permission Set Groups
↓
Restriction Rules
↓
Manual Sharing
↓
Login Policies
```

Result:\
✅ Employees → Own enrollments\
✅ Managers → Team access only\
✅ HR → Organization visibility\
✅ Secure login controls


