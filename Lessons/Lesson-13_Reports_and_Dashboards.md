## Lesson 13 — Reports & Dashboards (Business Visibility)

> Admins spend a lot of time building reports.

### Objective

By the end of this lesson:

1. Understand Reports
2. Report Types
3. Filters
4. Dashboard Components
5. Dynamic Dashboards
6. Real Project Analytics

---

### 1. What is a Report?

Report = Structured view of Salesforce data.

Used to answer:

```
What happened?
What is happening?
```

Examples:

- Employee certifications
- Course completion
- Enrollment counts

---

### 2. Report Structure

```
Object
  ↓
Filters
  ↓
Columns
  ↓
Output
```

Example:

```
Enrollment
  ↓
Status = Completed
  ↓
Show Employee
```

---

### 3. Report Types

#### Tabular

Simple list.

Example:

```
All Employees
```

---

#### Summary

Grouped report.

Example:

```
Courses grouped by Category
```

---

#### Matrix

Rows + Columns.

Example:

```
Department vs Completion
```

---

#### Joined

Multiple reports.

Example:

```
Enrollments + Certifications
```

---

### 4. Dashboard

Visual layer.

Displays:

- Charts
- Tables
- Metrics

Components:

```
Bar
Pie
Gauge
Metric
Table
```

---

### 5. Dynamic Dashboard

Runs using logged-in user access.

Example:

Manager sees:

```
Team Data
```

Employee sees:

```
Own Data
```

---

### 6. Project Dashboard

Employee Learning Dashboard:

```
Total Employees
Completed Courses
Pending Approvals
Certification Rate
```

---

### Knowledge Check

#### Q1. What is a Report?

A **Report** in Salesforce is a structured view of records used to analyze, filter, group, and summarize data.

Reports help answer questions like:

- How many employees completed training?
- Which courses have the highest enrollment?
- What is total course revenue?

Example:

```
Employee Name | Course | Status
```

Reports are data-focused.

---

#### Q2. Difference between Report and Dashboard?

| Report | Dashboard |
| --- | --- |
| Displays detailed data | Displays visual summaries |
| Table/list based | Charts and metrics |
| Source of dashboard data | Uses reports as source |
| Used for analysis | Used for monitoring |

Example:

- Report → List of enrollments
- Dashboard → Enrollment completion charts

Think:

```
Report = Data
Dashboard = Visualization
```

---

#### Q3. Difference between Summary and Matrix Report?

| Summary Report | Matrix Report |
| --- | --- |
| Groups by one field | Groups by rows and columns |
| Simpler aggregation | Multi-dimensional analysis |
| Good for totals | Good for comparisons |

Example:

Summary:

```
Department
  ↓
Employee Count
```

Matrix:

```
Department × Course Category
```

Example output:

| Department | Technical | Leadership |
| --- | --- | --- |
| DevOps | 20 | 5 |
| Salesforce | 15 | 8 |

---

#### Q4. What is Dynamic Dashboard?

A **Dynamic Dashboard** displays data according to the **logged-in user's access and permissions**.

Meaning:

- Employee sees own records
- Manager sees team records
- HR sees organization records

Example:

```
Same Dashboard
  ↓
Different View
  ↓
Based on User
```

Useful for personalized reporting.

---

#### Q5. Design dashboard for Employee Learning System

Dashboard Name:

```
Employee Learning Dashboard
```

**Components**

| Component | Type |
| --- | --- |
| Total Employees | Metric |
| Enrollment by Status | Donut Chart |
| Course Category Distribution | Pie Chart |
| Completed Courses by Department | Bar Chart |
| Monthly Enrollments | Line Chart |
| Certification Completion Rate | Gauge |

**Data Sources**

| Component | Report Source |
| --- | --- |
| Employee Summary | Employee Report |
| Enrollment Status | Enrollment Report |
| Course Analytics | Course Report |
| Certification Metrics | Enrollment + Employee Report |

**Filters**

Dashboard Filters:

| Filter | Values |
| --- | --- |
| Department | DevOps, Salesforce, Cloud |
| Course Category | Technical, Leadership |
| Enrollment Status | Enrolled, Completed |
| Date | Current Month, Quarter |

Dashboard Layout:

```
Top:
Total Employees | Completion Rate

Middle:
Enrollment Status | Course Categories

Bottom:
Monthly Trends | Department Analytics
```

This dashboard gives HR and Managers a complete learning overview in one place. ✅

---

