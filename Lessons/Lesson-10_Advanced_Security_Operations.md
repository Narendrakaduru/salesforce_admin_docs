## Lesson 10 — Advanced Security Operations

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


