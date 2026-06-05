## Lesson 9 — User Management, Licenses & Access Administration

> Salesforce security defines access rules. User Administration makes those rules operational.

### Objective

By the end of this lesson you will:

1. Understand Salesforce User Management
2. Learn User Licenses and their impact
3. Understand user creation lifecycle
4. Learn Profile and Permission assignment
5. Understand Freeze vs Deactivate
6. Learn login monitoring and access maintenance
7. Apply user administration to our Employee Learning & Certification Management System

---

### 1. What is User Management?

User Management is the process of creating, maintaining, controlling, and auditing Salesforce users.

Question answered:

> How do admins onboard and manage users?

Typical responsibilities:

- Create users
- Assign licenses
- Assign profiles
- Grant permissions
- Monitor usage
- Disable access

Flow:

```
Request
↓
Create User
↓
Assign Access
↓
Activate
↓
Monitor
```

Goal:

Provide users with the correct access and maintain security.

---

### 2. What is a User in Salesforce?

A User represents a person who can access Salesforce.

Each user normally has:

| Component | Purpose |
| --- | --- |
| Username | Login identity |
| User License | Platform entitlement |
| Profile | Base permissions |
| Role | Record visibility |
| Permission Sets | Additional access |

Relationship:

```
User
├── License
├── Profile
├── Role
└── Permission Sets
```

Example:

Employee:

```
Narendra
↓
Salesforce License
↓
Employee Profile
```

---

### 3. User Licenses

#### What is a User License?

User License determines what features a user is allowed to use.

Question answered:

> Can the user access a particular Salesforce capability?

Think:

```
License
↓
Feature Availability
```

Examples:

| License | Typical Usage |
| --- | --- |
| Salesforce | Full CRM access |
| Salesforce Platform | Platform apps |
| Identity | Authentication only |

Important:

License limits:

- Objects
- Features
- Profiles

Example:

```
User
↓
License
↓
Available Profiles
```

---

### 4. License → Profile Relationship

Rule:

Profile availability depends on license.

Process:

```
Choose License
↓
Eligible Profiles
↓
Assign User
```

Example:

```
Salesforce License
↓
Employee Profile
```

Not all profiles work with every license.

---

### 5. User Creation Lifecycle

Typical onboarding process:

```
Request
↓
Create User
↓
Assign License
↓
Assign Profile
↓
Assign Role
↓
Assign Permission Sets
↓
Activate
```

Steps:

1. Create User
2. Assign License
3. Assign Profile
4. Configure Role
5. Add Permission Sets
6. Verify Login

Navigate:

```
Setup
↓
Users
↓
New User
```

---

### 6. User Status Management

Refers to the lifecycle stages of a user.

Example:

```
Requested
↓
Active
↓
Suspended
↓
Disabled
```

Admin actions:

- Activate
- Freeze
- Deactivate
- Reset Password

---

### 7. Freeze vs Deactivate

This is a common interview topic.

| Freeze | Deactivate |
| --- | --- |
| Temporarily blocks login | Completely disables user |
| Keeps assignments | Releases license |
| Fast action | Administrative action |

Process:

```
User
↓
Freeze OR Deactivate
```

Important:

Deactivation may require cleanup:

- Running User
- Scheduled Jobs
- Ownership

---

### 8. Permission Assignment Strategy

Access should be layered.

Recommended order:

```
License
↓
Profile
↓
Permission Set
↓
Permission Set Group
```

Avoid:

```
Everyone
↓
Admin Profile
```

Good Example:

Employee:

```
Employee Profile
+
Course Access PS
```

Manager:

```
Manager Profile
+
Approval PS
```

---

### 9. Login Monitoring

Admins monitor user access.

Useful areas:

- Login History
- Failed Logins
- Session Monitoring
- Last Login

Process:

```
User Login
↓
Track
↓
Audit
```

Questions to monitor:

- Who logged in?
- Failed attempts?
- Inactive users?

---

### 10. Reset Password & Unlock User

Admins often support login issues.

Common actions:

#### Reset Password

Use when:

- User forgot password

Flow:

```
Admin
↓
Reset Password
↓
Email Sent
```

---

#### Unlock User

Use when:

- Too many failed logins

Flow:

```
Locked User
↓
Unlock
↓
Login Restored
```

---

### 11. User Adoption Monitoring

Admin responsibility:

Measure whether users actually use Salesforce.

Metrics:

| Metric | Meaning |
| --- | --- |
| Last Login | Activity |
| Active Users | Adoption |
| Session Count | Engagement |

Questions:

- Who stopped using system?
- Which teams need training?

---

### 12. Access Governance

Governance ensures correct access over time.

Lifecycle:

```
Create
↓
Assign
↓
Review
↓
Remove
```

Best Practices:

- Quarterly access review
- Remove unused permissions
- Disable inactive users
- Audit licenses

---

### Mini Project

Employee Learning & Certification Management System

Requirement:

Create secure onboarding.

User Setup:

| User | Configuration |
| --- | --- |
| Employee | Platform License + Employee Profile |
| Manager | Salesforce License + Manager Profile |
| HR | Salesforce License + HR Permission Group |

Lifecycle:

```
Employee Request
↓
Create User
↓
Assign License
↓
Assign Profile
↓
Assign Permissions
↓
Activate
```

Access Maintenance:

```
Leave
↓
Freeze

Exit
↓
Deactivate
```

Monitoring:

```
Login History
↓
Audit
```

---

### Hands-On

Perform:

1. Create User
2. Assign License
3. Assign Profile
4. Assign Permission Set
5. Freeze User
6. Reset Password
7. Review Login History

---

### Interview Questions

#### Q1. What determines available Profiles?

Answer:\
User License.

---

#### Q2. Difference between Freeze and Deactivate?

Answer:\
Freeze blocks login, but keeps the user record active and maintains assignment details. Deactivate completely disables access and releases the license for re-use.

---

#### Q3. Why use Permission Sets?

Answer:\
Grant additional permissions without changing profile.

---

### Knowledge Check

#### Q1. What is User Management?

**User Management** is the process of creating, maintaining, securing, and controlling user access in Salesforce.

Admin responsibilities include:

- Create users
- Assign licenses
- Assign profiles
- Assign permission sets
- Reset passwords
- Freeze/deactivate users
- Monitor login activity

Flow:

```
Create User
↓
Assign Access
↓
Monitor
↓
Maintain
```

---

#### Q2. What does a User License control?

A **User License** controls **what Salesforce features and functionality a user can access**.

It determines:

- Available profiles
- Apps/features available
- Object access capability

Example:

| License | Example Access |
| --- | --- |
| Salesforce | Full CRM access |
| Platform | Limited platform access |

Think:

```
License = Maximum possible access
↓
Profile = Actual permissions
```

---

#### Q3. Difference between Freeze and Deactivate?

| Freeze | Deactivate |
| --- | --- |
| Immediately blocks login | Removes active user access |
| User record remains active | User becomes inactive |
| Temporary action | Usually permanent/offboarding |
| Keeps assignments intact | Releases some usage |

Example:

- Employee on leave → Freeze
- Employee resigned → Deactivate

---

#### Q4. Explain user creation lifecycle.

User Lifecycle:

```
Request User
↓
Create User
↓
Assign License
↓
Assign Profile
↓
Assign Permission Sets
↓
Activate User
↓
Login Monitoring
↓
Freeze / Deactivate
```

Steps:

1. Create user record
2. Assign license
3. Assign profile
4. Assign permissions
5. Send login access
6. Monitor usage
7. Offboard if needed

---

#### Q5. Design onboarding process for Employee Learning System

Requirement:\
Provide secure onboarding for new employees.

##### User Creation

Admin creates:

```
Employee User
↓
Employee Details
↓
Activate
```

Fields:

- Name
- Email
- Username
- Role

---

##### License

Assign:

```
Salesforce Platform License
```

Purpose:\
Access Employee Learning application.

---

##### Profile

Assign profile:

| Role | Profile |
| --- | --- |
| Employee | Learning Employee Profile |
| Manager | Learning Manager Profile |
| HR | Learning Admin Profile |

Controls:

- Object permissions
- Tabs
- Apps

---

##### Permission Assignment

Assign Permission Sets:

| Permission Set | Purpose |
| --- | --- |
| Enrollment Access | Manage enrollments |
| Course Access | View courses |
| Reporting Access | View dashboards |

Optional:

```
Permission Set Group
↓
Learning_User_PSG
```

---

##### Login Monitoring

Monitor:

```
Setup
↓
Login History
```

Track:

- Login success/failure
- IP address
- Login time
- User activity

Policies:

```
MFA Enabled
↓
Business Hours Login
↓
Session Timeout
```

Complete Onboarding Flow:

```
Create User
↓
Assign License
↓
Assign Profile
↓
Assign Permission Sets
↓
Send Credentials
↓
Monitor Login
↓
Audit Access
```

Result:

✅ Employees get required access only\
✅ Managers receive team visibility\
✅ HR receives administrative access\
✅ Secure onboarding and monitoring process

