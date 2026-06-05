## Lesson 16 — Data Management (Import, Export & Data Quality)

> Good automation on bad data still produces bad results. Data quality is one of the most important responsibilities of a Salesforce Admin.

### Objective

By the end of this lesson you will:

1. Understand Salesforce Data Management
2. Learn Data Import Wizard
3. Learn Data Loader
4. Understand Duplicate Rules
5. Learn Data Quality practices
6. Understand backup strategies
7. Apply data operations to our Employee Learning & Certification Management System

---

### 1. What is Data Management?

Data Management is the process of:

- Importing data
- Exporting data
- Cleaning records
- Preventing duplicates
- Maintaining data quality
- Protecting business information

Examples of Salesforce data:

- Employees
- Courses
- Enrollments
- Certifications
- Reports

Goal:

```
Collect
↓
Validate
↓
Store
↓
Maintain
↓
Analyze
```

Why it matters:

- Better reporting
- Reliable automation
- Accurate dashboards
- Better user adoption

---

### 2. Data Import Overview

Import means bringing external data into Salesforce.

Common sources:

- CSV files
- Excel spreadsheets
- HR systems
- ERP systems
- Legacy applications

Typical import process:

```
Source Data
↓
Prepare CSV
↓
Map Fields
↓
Validate
↓
Import
↓
Verify
```

Common imported objects:

| Object | Example |
| --- | --- |
| Employee | Employee list |
| Course | Course catalog |
| Enrollment | Learning registrations |
| Certification | Existing certifications |

---

### 3. Data Import Wizard

Data Import Wizard is Salesforce's browser-based import tool.

Best for:

- Small and medium imports
- Admin-friendly uploads
- Simple updates

Navigation:

```
Setup
↓
Data Import Wizard
```

Supports:

| Feature | Supported |
| --- | --- |
| Insert | Yes |
| Update | Yes |
| Delete | No |
| Duplicate Detection | Yes |

Advantages:

- Easy to use
- No installation
- Guided mapping

Limitations:

- Less control
- Limited volume

Example:

Import Employees.

CSV:

```
Employee Name,Email,Department
Narendra,user1@example.com,Salesforce
Rahul,user2@example.com,DevOps
```

---

### 4. Data Loader

Data Loader is Salesforce's advanced bulk data tool.

Used for:

- Large imports
- Updates
- Exports
- Deletes
- Migration

Process:

```
Open Data Loader
↓
Select Operation
↓
Upload CSV
↓
Map Fields
↓
Execute
```

Operations:

| Operation | Supported |
| --- | --- |
| Insert | Yes |
| Update | Yes |
| Upsert | Yes |
| Export | Yes |
| Delete | Yes |
| Hard Delete | Yes |

---

### 5. Import Wizard vs Data Loader

| Feature | Import Wizard | Data Loader |
| --- | --- | --- |
| Interface | Browser | Application |
| Volume | Small | Large |
| Export | No | Yes |
| Delete | No | Yes |
| Complexity | Simple | Advanced |

Selection:

```
Simple Import
↓
Import Wizard

Migration
↓
Data Loader
```

---

### 6. What is Upsert?

Upsert means:

```
Update
+
Insert
```

Behavior:

```
Record Exists
↓
Update

Record Missing
↓
Insert
```

Used with:

- External IDs
- Integrations
- Synchronization

Example:

Employee already exists:

Update.

Employee not found:

Create.

---

### 7. Duplicate Rules

Duplicate Rules prevent duplicate records.

Question answered:

> How do we stop users from creating repeated records?

Example:

```
Same Email
↓
Duplicate Found
↓
Block Save
```

Two related concepts:

---

#### Matching Rule

Defines how duplicates are detected.

Examples:

- Email
- Employee ID
- Name

---

#### Duplicate Rule

Defines what action happens.

Actions:

- Allow
- Alert
- Block

Example:

```
Email Match
↓
Show Warning
```

---

### 8. Data Quality

Data Quality means maintaining accurate records.

Problems:

- Missing values
- Duplicates
- Invalid formats
- Outdated records

Improve quality using:

- Validation Rules
- Required Fields
- Picklists
- Duplicate Rules

Process:

```
Enter
↓
Validate
↓
Store
↓
Monitor
```

Good Data:

```
Consistent
Accurate
Complete
```

---

### 9. Data Cleanup

Admins regularly clean data.

Methods:

- Merge duplicates
- Remove invalid records
- Standardize values
- Archive old data

Example:

Bad:

```
DevOpsdevopsDEVOPS
```

Good:

```
DevOps
```

---

### 10. Exporting Data

Export means extracting Salesforce records.

Reasons:

- Backup
- Reporting
- Migration
- Recovery

Process:

```
Salesforce
↓
Select Objects
↓
Generate Export
↓
Download
```

Export Types:

| Type | Description |
| --- | --- |
| Manual | One-time |
| Scheduled | Automatic |

---

### 11. Backup Strategies

Admins should never rely on production alone.

Backup before:

- Deployments
- Bulk updates
- Cleanup
- Migration

Recommended strategy:

```
Export
↓
Store Securely
↓
Version Backup
```

Backup Checklist:

- Employee
- Course
- Enrollment
- Certification

---

### 12. Import Error Handling

Import results:

```
Import
├── Success
└── Failed Records
```

Common failures:

| Error | Cause |
| --- | --- |
| Required Field Missing | Empty value |
| Duplicate Found | Duplicate Rule |
| Invalid Picklist | Wrong value |

Recovery:

```
Review Errors
↓
Fix CSV
↓
Retry
```

---

### Mini Project

Employee Learning & Certification Management System

Scenario:

Import employees into Employee object.

CSV:

```
Employee Name,Email,Department,Experience
Narendra,user1@example.com,Salesforce,4
Rahul,user2@example.com,DevOps,5
Priya,user3@example.com,Cloud,6
```

Process:

```
Prepare CSV
↓
Import Wizard
↓
Map Fields
↓
Validate
↓
Employee Created
```

Duplicate Prevention:

```
Email
↓
Matching Rule
↓
Duplicate Rule
↓
Block Duplicate
```

Backup Plan:

```
Weekly Export
↓
Secure Storage
```

---

### Hands-On

Perform:

1. Create Employee CSV
2. Open Data Import Wizard
3. Import Employee records
4. Verify records
5. Configure Duplicate Rule
6. Export Employee data

---

### Interview Questions

#### Q1. Difference between Import Wizard and Data Loader?

Answer:\
Import Wizard is simpler and browser-based, whereas Data Loader is an advanced application that supports larger volumes and bulk operations.

---

#### Q2. What is Upsert?

Answer:\
Upsert matches incoming records against existing ones; it updates existing records and inserts new ones.

---

#### Q3. Why use Duplicate Rules?

Answer:\
To prevent duplicate records from being created, ensuring data cleanliness and quality.

---

### Knowledge Check

#### Q1. What is Data Management?

**Data Management** is the process of importing, exporting, updating, cleaning, maintaining, and protecting data inside Salesforce.

Common activities:

- Import records
- Export records
- Update records
- Delete records
- Prevent duplicates
- Maintain data quality

Example:

```
CSV
↓
Import
↓
Validate
↓
Store in Salesforce
```

---

#### Q2. Difference between Import Wizard and Data Loader?

| Data Import Wizard | Data Loader |
| --- | --- |
| Browser-based | Desktop/client tool |
| Easy for admins | More powerful |
| Supports standard import operations | Supports Insert, Update, Upsert, Export, Delete |
| Smaller datasets | Large datasets |

Example:

- Import 500 employees → Import Wizard
- Import 100,000 employees → Data Loader

---

#### Q3. What is Upsert?

**Upsert = Update + Insert**

Salesforce checks whether a record already exists:

- Exists → Update
- Doesn't exist → Insert

Usually uses:

- Record ID
- External ID

Example:

CSV:

| Employee ID | Name |
| --- | --- |
| EMP001 | Narendra |
| EMP002 | Ravi |

Result:

- EMP001 exists → Update
- EMP002 missing → Create

Flow:

```
Match
↓
Update OR Insert
```

---

#### Q4. What is the difference between Matching Rule and Duplicate Rule?

| Matching Rule | Duplicate Rule |
| --- | --- |
| Defines how duplicates are identified | Defines what action happens |
| Comparison logic | Prevention logic |
| Runs behind the scenes | Blocks or warns users |

Example:

Matching Rule:

```
Email = Exact Match
```

Duplicate Rule:

```
Block save if duplicate found
```

Think:

```
Matching Rule → Detect
↓
Duplicate Rule → Act
```

---

#### Q5. Design a safe employee import process

Requirement:\
Import employees safely with duplicate prevention.

##### Step 1 — Prepare CSV

Example:

| Employee ID | Name | Email | Department |
| --- | --- | --- | --- |

Rules:

- Clean formatting
- Mandatory columns
- Unique Employee IDs

---

##### Step 2 — Import Tool

Recommended:

```
Data Import Wizard
```

For large files:

```
Data Loader
```

Operation:

```
Upsert
```

Reason:\
Avoid duplicate employee creation.

---

##### Step 3 — Duplicate Prevention

Configure:

Matching Rule:

```
Email Exact Match
Employee ID Exact Match
```

Duplicate Rule:

```
Block duplicate creation
Show warning
```

Flow:

```
Import
↓
Check Duplicate
↓
Allow / Reject
```

---

##### Step 4 — Target Backup Strategy

Before import:

```
Export Existing Employees
↓
CSV Backup
↓
Store Securely
```

After import:

- Verify counts
- Run reports
- Validate sample records

Complete Process:

```
Backup
↓
Prepare CSV
↓
Configure Matching Rule
↓
Enable Duplicate Rule
↓
Import (Upsert)
↓
Validate
↓
Audit
```

This gives a **safe, recoverable, duplicate-controlled employee import process** in Salesforce. ✅

---

