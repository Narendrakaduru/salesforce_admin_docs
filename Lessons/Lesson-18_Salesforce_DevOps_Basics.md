## Lesson 18 — Salesforce DevOps Basics

> Building features is important. Delivering changes safely, repeatedly, and predictably is what makes teams scalable.

### Objective

By the end of this lesson you will:

1. Understand Salesforce DevOps fundamentals
2. Learn version control concepts
3. Understand environment strategy
4. Learn CI/CD basics for Salesforce
5. Understand deployment automation
6. Learn release governance
7. Apply DevOps practices to our Employee Learning & Certification Management System

---

### 1. What is Salesforce DevOps?

Salesforce DevOps is the practice of managing development, testing, deployment, and releases in a controlled and automated way.

Goal:

```
Plan
↓
Build
↓
Test
↓
Deploy
↓
Monitor
```

Traditional approach:

```
Build
↓
Manual Deploy
↓
Production
```

DevOps approach:

```
Build
↓
Version Control
↓
Automated Validation
↓
Deploy
```

Benefits:

- Faster releases
- Reduced deployment risk
- Better collaboration
- Repeatable delivery

---

### 2. Why Salesforce Needs DevOps

Salesforce development includes:

- Objects
- Flows
- Validation Rules
- Reports
- Security
- Metadata

Without process:

Problems:

```
Broken Deployments
↓
Missing Components
↓
Production Errors
```

With DevOps:

```
Controlled Releases
↓
Predictable Delivery
```

---

### 3. Salesforce Metadata

Salesforce primarily deploys metadata.

Examples:

| Metadata | Example |
| --- | --- |
| Object | Employee |
| Field | Department |
| Flow | Enrollment Automation |
| Validation Rule | Course Cost Check |
| Dashboard | Learning Dashboard |

Not metadata:

- Employee Records
- Course Records

Think:

```
Structure = Metadata
Business Records = Data
```

---

### 4. Version Control (Very Important)

Version Control tracks changes.

Question answered:

> How do teams know who changed what?

Benefits:

- History
- Collaboration
- Rollback
- Branching

Flow:

```
Developer
↓
Commit
↓
Repository
↓
Review
↓
Deploy
```

Typical workflow:

```
Build
↓
Commit
↓
Review
↓
Merge
```

Version control tracks:

- Objects
- Flows
- Layouts
- Security

---

### 5. Branching Strategy

Branches isolate work.

Common approach:

```
Main
├── Feature
├── Bugfix
└── Release
```

Example:

```
main
└── enrollment-approval-feature
```

Benefits:

- Safe development
- Parallel work
- Easier rollback

---

### 6. CI (Continuous Integration)

CI validates changes frequently.

Question answered:

> How do teams detect issues early?

Process:

```
Change
↓
Build
↓
Validate
↓
Test
```

CI Activities:

- Validate metadata
- Run tests
- Check dependencies

Benefits:

- Early error detection
- Faster feedback

---

### 7. CD (Continuous Delivery)

CD prepares safe deployments.

Question answered:

> How do changes reach users reliably?

Process:

```
Validated Build
↓
Approval
↓
Deploy
```

Example:

```
Sandbox
↓
UAT
↓
Production
```

Benefits:

- Predictable releases
- Lower production risk

---

### 8. Environment Strategy

Recommended environment model:

```
Developer Sandbox
↓
Integration
↓
UAT
↓
Production
```

Purpose:

| Environment | Purpose |
| --- | --- |
| Developer | Build |
| Integration | Combine changes |
| UAT | Business validation |
| Production | Live system |

Rule:

Never build directly in Production.

---

### 9. Deployment Approaches

Salesforce deployments may use:

| Method | Usage |
| --- | --- |
| Change Sets | Manual deployment |
| Metadata Deployment | Controlled release |
| Automated Pipeline | Enterprise delivery |

Deployment Flow:

```
Build
↓
Validate
↓
Deploy
↓
Verify
```

---

### 10. Release Management

Release Management organizes changes.

Lifecycle:

```
Requirement
↓
Build
↓
Test
↓
Approve
↓
Release
↓
Monitor
```

Release Types:

| Type | Description |
| --- | --- |
| Major | Large feature |
| Minor | Enhancement |
| Hotfix | Urgent fix |

---

### 11. Deployment Governance

Governance reduces production failures.

Checklist:

- Change approval
- Validation
- Backup
- Deployment window
- Rollback plan

Example:

```
Change Request
↓
Approve
↓
Deploy
↓
Smoke Test
```

---

### 12. Rollback Strategy

Question answered:

> What happens if deployment fails?

Process:

```
Deploy
├── Success
└── Failure
     ↓
    Rollback
```

Methods:

- Restore metadata
- Restore data backup
- Redeploy previous release

Goal:

Recover quickly.

---

### 13. Monitoring After Release

Deployment is not the end.

Monitor:

- Errors
- User adoption
- Performance
- Login activity

Flow:

```
Deploy
↓
Observe
↓
Improve
```

---

### Mini Project

Employee Learning & Certification Management System

Requirement:

Deploy enrollment improvements safely.

Changes:

- New Enrollment Fields
- Approval Flow
- Certification Updates
- Dashboard Updates

DevOps Flow:

```
Build
↓
Version Control
↓
Validate
↓
Deploy UAT
↓
Approve
↓
Production
```

Environment Strategy:

```
Developer Sandbox
↓
Integration
↓
UAT
↓
Production
```

Release Checklist:

- Backup
- Validate
- Deploy
- Smoke Test
- Monitor

---

### Hands-On

Perform:

1. Create deployment checklist
2. Define environment flow
3. Document rollback plan
4. Create release notes
5. Simulate deployment approval

---

### Interview Questions

#### Q1. What is Salesforce DevOps?

Answer:\
Controlled delivery and release management for Salesforce changes.

---

#### Q2. Why use Version Control?

Answer:\
Track history and manage collaboration.

---

#### Q3. Difference between CI and CD?

Answer:\
CI focuses on automated validation and testing of changes frequently, whereas CD focuses on the automatic or streamlined deployment of validated builds to staging and production environments.

---

### Knowledge Check

#### Q1. What is Salesforce DevOps?

**Salesforce DevOps** is the practice of managing Salesforce changes using automation, version control, testing, deployment processes, and monitoring.

Goal:

- Faster releases
- Fewer production issues
- Better collaboration
- Traceable changes

Typical flow:

```
Build
↓
Track
↓
Test
↓
Deploy
↓
Monitor
```

Examples:

- Deploy Flows
- Deploy Objects/Fields
- Deploy Validation Rules
- Release UI changes

---

#### Q2. Why is Version Control important?

**Version Control** stores and tracks changes made to Salesforce metadata over time.

Benefits:

- Change history
- Rollback capability
- Team collaboration
- Prevent overwrite conflicts
- Controlled releases

Example:

```
Validation Rule v1
↓
Validation Rule v2
↓
Restore if needed
```

Common practice:\
Store metadata in Git.

Think:

```
Version Control = Single Source of Truth
```

---

#### Q3. Explain CI vs CD.

| CI (Continuous Integration) | CD (Continuous Deployment/Delivery) |
| --- | --- |
| Merge and validate changes frequently | Deploy validated changes automatically |
| Focus on testing | Focus on release |
| Detect issues early | Deliver faster |

Example:

CI:

```
Commit
↓
Validate
↓
Run Tests
```

CD:

```
Approved Build
↓
Deploy
↓
Release
```

---

#### Q4. What should happen before deployment?

Before deployment:

1. Complete development
2. Peer review
3. Run validation
4. Execute tests
5. Check dependencies
6. Obtain approval
7. Prepare rollback plan

Flow:

```
Build
↓
Validate
↓
Test
↓
Approve
↓
Deploy
```

Reason:\
Reduce production failures.

---

#### Q5. Design DevOps process for Employee Learning System

Requirement:\
Deploy enhancements safely.

##### Version Control

Store:

```
Employee Object
Course Object
Enrollment Flow
Validation Rules
Reports
```

Repository structure:

```
main
develop
feature/*
```

Purpose:\
Track all changes.

---

##### Environment Strategy

Environment Flow:

```
Developer Sandbox
↓
Integration Sandbox
↓
UAT Sandbox
↓
Production
```

Usage:

| Environment | Purpose |
| --- | --- |
| Developer | Build |
| Integration | Combined testing |
| UAT | Business validation |
| Production | Live |

---

##### Validation

Validate:

```
Metadata
Dependencies
Flows
Permissions
Tests
```

Checklist:

```
No validation errors
Tests pass
Approval complete
```

---

##### Deployment

Deployment process:

```
Create Release
↓
Deploy Metadata
↓
Run Tests
↓
Verify
↓
Enable Users
```

Deploy:

- Enrollment enhancements
- Approval process
- Dashboard updates
- Security changes

---

##### Monitoring

Monitor:

```
Deployment Status
Login History
Flow Errors
Reports
User Feedback
```

Track:

- Failed deployments
- Performance
- Adoption

Complete DevOps Flow:

```
Version Control
↓
Developer Sandbox
↓
Validate
↓
Deploy
↓
Production
↓
Monitor
```

Result:

✅ Controlled releases\
✅ Safer deployments\
✅ Better quality\
✅ Faster delivery for Employee Learning System
