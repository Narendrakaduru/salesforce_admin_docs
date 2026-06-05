## Lesson 12 — Approval Processes (Enterprise Automation)

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

