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

