## Lesson 19 — Employee Learning & Certification Management System (Real Enterprise Project)

> By the end of this lesson, you should have a working Salesforce application with real objects and relationships — not just theory.

### Phase 1 — Requirement → Architecture → Create Application → Create Objects → Create Fields

---

### 0. Before We Build — Understand What We Are Building

Imagine your company says:

> "We want an internal portal where employees can learn courses, managers approve enrollments, HR tracks certifications, and leadership sees dashboards."

As Salesforce Admins, we convert business requirements into Salesforce.

Business:

```
Learning System
```

Salesforce:

```
App
↓
Objects
↓
Fields
↓
Relationships
↓
Security
↓
Automation
↓
Reports
```

---

### 1. Understand the Business Requirement

Company wants employees to:

- Login
- View profile
- Browse courses
- Enroll
- Request approval
- Complete training
- Receive certification
- View progress

Managers should:

- Approve requests
- Monitor teams

HR should:

- Monitor all employees

Admin should:

- Configure system

---

### 2. Convert Requirement into Architecture

Question:

> What data do we need?

Answer:

```
Employee
Course
Enrollment
Certification
Skill
```

Architecture:

```
Employee
│
├──── Skills
│
├──── Certifications
│
└──── Enrollments
           │
           ▼
         Course
```

Meaning:

Employee:

```
One Employee
↓
Many Skills

One Employee
↓
Many Certifications

Many Employees
↓
Many Courses
↓
Enrollment
```

---

### 3. Create the Application (Container)

Think:

```
Application = Folder
Objects = Files
```

Navigate:

```
Setup
↓
App Manager
↓
New Lightning App
```

Fill:

App Name:

```
Employee Learning System
```

Developer Name:

```
Employee_Learning_System
```

Description:

```
Internal Learning Management Application
```

Click:

```
Next
```

Select Navigation:

```
Standard Navigation
```

Click:

```
Next
```

Add Tabs:

Leave empty for now.

Save.

Result:

You created the application.

---

### 4. Create First Object — Employee

Question:

> Where will employee information be stored?

Answer:

Employee Object.

Navigate:

```
Setup
↓
Object Manager
↓
Create
↓
Custom Object
```

Fill:

Label:

```
Employee
```

Plural:

```
Employees
```

Record Name:

```
Employee ID
```

Data Type:

```
Auto Number
```

Display Format:

```
EMP-{0000}
```

Example:

```
EMP-0001
EMP-0002
```

Starting Number:

```
1
```

Enable:

☑ Allow Reports\
☑ Track Activities\
☑ Track Field History

Save.

You created Employee.

---

### 5. Understand Objects, Fields and Records

Example:

Employee Object:

| Employee ID | First Name | Department |
| --- | --- | --- |
| EMP-001 | Narendra | Salesforce |

Meaning:

Object:

```
Employee
```

Fields:

```
ID
Name
Department
```

Record:

```
Narendra
```

---

### 6. Create Employee Fields (Very Detailed)

Navigate:

```
Employee
↓
Fields & Relationships
↓
New
```

Create field one by one.

---

#### Field 1

Select:

```
Text
```

Next

Field Label:

```
First Name
```

Length:

```
50
```

Required:

☑

Save.

---

#### Field 2

Create:

```
Last Name
```

Type:

```
Text
```

Save.

---

#### Field 3

Create:

```
Email
```

Type:

```
Email
```

Required:

☑

Save.

---

#### Field 4

Create:

```
Department
```

Type:

```
Picklist
```

Values:

```
Salesforce
DevOps
Cloud
ServiceNow
Cybersecurity
```

Save.

Why Picklist?

Because:

```
Controlled Values
↓
No Mistakes
```

---

#### Field 5

Create:

```
Experience
```

Type:

```
Number
```

Length:

```
2
```

Decimal:

```
0
```

Save.

---

#### Field 6

Create:

```
Joining Date
```

Type:

```
Date
```

Save.

---

#### Field 7

Create:

```
Is Certified
```

Type:

```
Checkbox
```

Default:

```
False
```

Save.

---

Employee is complete.

---

### 7. Create Skill Object

Question:

> Where do employee skills get stored?

Business says:

One Employee can have multiple skills.

Example:

```
Narendra
↓
Salesforce
↓
DevOps
↓
AWS
```

Create:

```
Setup
↓
Object Manager
↓
Create
↓
Custom Object
```

Fill:

| Field | Value |
| --- | --- |
| Label | Skill |
| Plural | Skills |
| Record Name | Skill Name |
| Data Type | Text |

Enable:

☑ Allow Reports\
☑ Track Activities

Save.

---

#### Create Skill Fields

Navigate:

```
Skill
↓
Fields & Relationships
↓
New
```

Create:

| Field | Type |
| --- | --- |
| Skill Category | Picklist |
| Skill Level | Picklist |
| Employee | Lookup(Employee) |

Skill Category:

```
Technical
Leadership
Business
```

Skill Level:

```
Beginner
Intermediate
Advanced
Expert
```

Architecture:

```
Employee
↓
Skill
```

Meaning:

```
One Employee
↓
Many Skills
```

---

### 8. Create Course Object

Question:

> Where are courses stored?

Create:

```
Course
```

Record Name:

```
Course Name
```

Fields:

| Field | Type |
| --- | --- |
| Category | Picklist |
| Duration Hours | Number |
| Cost | Currency |
| Active | Checkbox |
| Description | Long Text |

Category:

```
Technical
Leadership
Certification
```

Save.

---

### 9. Create Enrollment (Most Important)

Business says:

```
One Employee → Many Courses
One Course → Many Employees
```

Salesforce says:

Many-to-Many.

Solution:

```
Employee
↓
Enrollment
↓
Course
```

Create:

Object:

```
Enrollment
```

Record Name:

```
Enrollment ID
```

Type:

```
Auto Number
```

Save.

---

### 10. Create Certification Object

Question:

> Where do completed certifications get stored?

Business Requirement:

Employees complete courses and receive certifications.

Navigate:

```
Setup
↓
Object Manager
↓
Create
↓
Custom Object
```

Fill:

| Field | Value |
| --- | --- |
| Label | Certification |
| Plural | Certifications |
| Record Name | Certification ID |
| Type | Auto Number |

Display Format:

```
CERT-{0000}
```

Starting Number:

```
1
```

Enable:

☑ Reports\
☑ Activities

Save.

---

#### Create Certification Fields

Navigate:

```
Certification
↓
Fields & Relationships
↓
New
```

Create:

| Field | Type |
| --- | --- |
| Certification Name | Text |
| Completion Date | Date |
| Expiry Date | Date |
| Score | Percent |
| Employee | Lookup(Employee) |

Meaning:

```
Employee
↓
Certification
```

Result:

```
One Employee
↓
Many Certifications
```

---

### 11. Create Relationship — Employee to Enrollment

Navigate:

```
Enrollment
↓
Fields
↓
New
```

Choose:

```
Master Detail
```

Select:

```
Employee
```

Save.

Meaning:

Enrollment belongs to Employee.

---

### 12. Create Relationship — Course to Enrollment

Navigate:

```
Enrollment
↓
Fields
↓
New
```
Choose:

```
Master Detail
```

Select:

```
Course
```

Save.

Now relationship:

```
Employee
↓
Enrollment
↓
Course
```

Many-to-Many created.

---

### 13. Add Enrollment Fields

Create:

| Field | Type |
| --- | --- |
| Enrollment Date | Date |
| Status | Picklist |
| Completion | Percent |

Status:

```
Enrolled
In Progress
Completed
Cancelled
```

Save.

---

### 14. Create Object Tabs

Navigate:

```
Setup
↓
Tabs
↓
New
```

Choose:

```
Custom Object Tab
```

Create tabs:

```
Employee
Skill
Course
Enrollment
Certification
```

Choose any icon.

Save.

Reason:

```
Object
↓
Creates Tab
↓
Tab Added To App
```

---

### 15. Add Tabs to Employee Learning System App

Do this after creating:

```
Employee
Course
Enrollment
Skill
Certification
```

---

#### Method 1 (Recommended) — From App Manager

Navigate:

```
Setup
↓
App Manager
```

Search:

```
Employee Learning System
```

Click:

```
▼ Edit
```

Open:

```
Navigation Items
```

You will see:

```
Available Items
← →
Selected Items
```

---

#### Add Tabs

Search and move one by one:

Move →

```
Employee
```

Move →

```
Course
```

Move →

```
Enrollment
```

Move →

```
Skill
```

Move →

```
Certification
```

Also add:

```
Reports
Dashboards
```

---

#### Arrange Order

Recommended order:

```
Home
Employee
Skill
Course
Enrollment
Certification
Reports
Dashboards
```

Use:

```
↑
↓
```

to reorder.

---

#### Save

Click:

```
Save
```

---

### Verify Tabs

Navigate:

```
App Launcher
↓
Employee Learning System
```

Expected:

```
Employee Learning System
Home
Employee
Skill
Course
Enrollment
Certification
Reports
Dashboards
```

---

### Why We Add Tabs After Objects?

Because:

```
Object
↓
Generates Tab
↓
Tab added into App
```

If object does not exist:

```
No Object
↓
No Tab
```

---

### 16. Validate Build

Create records.

Employee:

```
Narendra
```

Skill:

```
Salesforce Admin
Advanced
```

Course:

```
Salesforce Administrator
```

Enrollment:

```
Narendra
↓
Salesforce Administrator
```

Certification:

```
Salesforce Administrator Certification
```

Open Employee.

Verify Related Lists:

```
Skills
Enrollments
Certifications
```

If visible:

```
Build Successful
```

### End of Phase 1

Completed:

```
Application
↓
Employee
↓
Skill
↓
Course
↓
Enrollment
↓
Certification
↓
Relationships
↓
Tabs
↓
Sample Data
↓
Validation
```

---
