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
