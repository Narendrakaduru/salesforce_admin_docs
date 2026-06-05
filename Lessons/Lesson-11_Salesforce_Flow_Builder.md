## Lesson 11 — Salesforce Flow Builder

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

