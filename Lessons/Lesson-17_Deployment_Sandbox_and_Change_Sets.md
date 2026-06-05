## Lesson 17 — Deployment, Sandbox, Change Sets & Release Management

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


