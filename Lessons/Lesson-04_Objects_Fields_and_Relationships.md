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

