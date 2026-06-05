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

