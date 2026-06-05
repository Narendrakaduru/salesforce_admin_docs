## Lesson 15 — UI & Productivity

> A good Salesforce application is not only functional—it should also be easy, fast, and intuitive for users.

### Objective

By the end of this lesson you will:

1. Understand Page Layouts
2. Learn Record Types
3. Build Lightning Pages
4. Understand Dynamic Forms
5. Learn Global Actions
6. Improve user productivity
7. Apply UI design to our Employee Learning & Certification Management System

---

### 1. What is UI & Productivity in Salesforce?

UI (User Interface) determines how users interact with Salesforce.

Productivity features help users:

- Work faster
- Reduce clicks
- Improve user experience
- View relevant information
- Complete actions efficiently

Think:

```
Data
↓
Page Design
↓
User Experience
↓
Productivity
```

Salesforce provides:

- Page Layouts
- Record Types
- Lightning App Builder
- Dynamic Forms
- Global Actions

---

### 2. Page Layouts

Page Layout controls:

- Field placement
- Related lists
- Buttons
- Sections
- Visibility

Question answered:

> What does the user see on a record page?

Navigate:

```
Setup
↓
Object Manager
↓
Object
↓
Page Layouts
```

Example:

Employee Layout:

```
Employee Information
├── Name
├── Email
└── Department

Learning Information
├── Courses
└── Certifications
```

Capabilities:

- Add fields
- Remove fields
- Reorder sections
- Add buttons

Best Practices:

- Keep important fields at top
- Group related information
- Reduce scrolling

---

### 3. Record Types

Record Types allow different business processes for the same object.

Question answered:

> Should different users see different record experiences?

Example:

Object:

```
Course
```

Record Types:

```
Technical
Leadership
Compliance
```

Each Record Type can control:

- Picklist values
- Business process
- Page Layout

Example:

Technical Course:

```
Category:
Cloud
DevOps
Salesforce
```

Leadership Course:

```
Category:
Management
Communication
```

Navigation:

```
Object Manager
↓
Object
↓
Record Types
```

---

### 4. Record Type + Page Layout Relationship

Record Types and Page Layouts often work together.

Example:

```
Record Type
↓
Choose Layout
↓
Display Fields
```

Example:

Employee Role:

```
Manager
↓
Manager Layout
```

Employee Role:

```
Learner
↓
Learner Layout
```

Result:

Different UI for different users.

---

### 5. Lightning App Builder

Lightning App Builder creates pages using drag-and-drop components.

Purpose:

Build custom UI.

Navigate:

```
Setup
↓
Lightning App Builder
```

Page Types:

| Page | Purpose |
| --- | --- |
| App Page | Application pages |
| Home Page | Landing page |
| Record Page | Object records |

Example:

Employee Dashboard Page:

```
Header
├── Employee Summary
├── Certifications
└── Enrollment Metrics
```

Capabilities:

- Add components
- Rearrange sections
- Configure visibility

---

### 6. Dynamic Forms

Dynamic Forms make pages intelligent.

Question answered:

> Can Salesforce show fields only when needed?

Answer:

Yes.

Example:

If:

```
Course Type = Certification
```

Show:

```
Certification Expiry
```

Otherwise:

Hide.

Flow:

```
Condition
↓
Evaluate
↓
Show Component
```

Benefits:

- Cleaner UI
- Better experience
- Reduced clutter

Example:

Employee:

```
Certified = True
↓
Show Certification Section
```

---

### 7. Component Visibility

Control when components appear.

Rules can depend on:

- User Role
- Record Value
- Device Type
- Profile

Example:

```
Manager
↓
Show Approval Component
```

Employee:

```
Hide Approval Component
```

---

### 8. Global Actions

Global Actions allow users to perform quick actions.

Question answered:

> How can users create records faster?

Examples:

- Create Employee
- Log Activity
- Create Enrollment

Navigation:

```
Setup
↓
Global Actions
```

Example:

Click:

```
New Enrollment
```

Immediately:

```
Open Form
↓
Create Record
```

Benefits:

- Faster navigation
- Fewer clicks
- Better productivity

---

### 9. Quick Actions vs Global Actions

| Quick Action | Global Action |
| --- | --- |
| Object specific | Available globally |
| Context aware | Universal |
| Related records | Standalone |

Example:

Quick Action:

```
Create Certification
```

Global Action:

```
Create Enrollment
```

---

### 10. Mobile Productivity

Salesforce UI supports mobile optimization.

Examples:

- Compact Layout
- Dynamic Actions
- Responsive Components

Goal:

```
Desktop
+
Mobile
=
Consistent Experience
```

---

### Mini Project

Employee Learning & Certification Management System

Design:

Employee UI

```
Employee
├── Profile Section
├── Skill Section
├── Certification Section
└── Enrollment History
```

Record Types:

```
Course
├── Technical
└── Leadership
```

Dynamic Form:

```
Certified = True
↓
Show Certification Details
```

Global Action:

```
Create Enrollment
```

Lightning Page:

```
Employee Dashboard
```

---

### Hands-On

Perform:

1. Open Object Manager
2. Select Employee Object
3. Create Page Layout
4. Create Record Type
5. Open Lightning App Builder
6. Create Record Page
7. Add Dynamic Visibility

---

### Interview Questions

#### Q1. Difference between Page Layout and Record Type?

Answer:\
Page Layout controls UI layout, whereas Record Type controls business process variation.

---

#### Q2. Why use Dynamic Forms?

Answer:\
Show relevant fields conditionally.

---

#### Q3. When should Global Actions be used?

Answer:\
For fast record creation from anywhere in the application.

---

### Knowledge Check

#### Q1. What does Page Layout control?

A **Page Layout** controls how fields, sections, buttons, related lists, and actions appear to users on a record page.

Page Layout controls:

- Field visibility
- Field order
- Required fields
- Related lists
- Quick actions

Example:

```
Employee Page
↓
Employee Details
↓
Enrollment History
↓
Actions
```

Page Layout controls **how the page looks and behaves**.

---

#### Q2. Difference between Record Type and Page Layout?

| Record Type | Page Layout |
| --- | --- |
| Controls business process and record variations | Controls UI arrangement |
| Can show different picklist values | Controls field placement |
| Used for different user scenarios | Used for page design |

Example:

Record Types:

```
Technical Course
Leadership Course
```

Page Layout:

```
Fields shown differently for each type
```

Think:

- **Record Type → Which version**
- **Page Layout → How it looks**

---

#### Q3. What is Lightning App Builder?

**Lightning App Builder** is a drag-and-drop tool used to create and customize Lightning pages.

Used for:

- App Pages
- Home Pages
- Record Pages

Features:

- Add components
- Rearrange UI
- Configure visibility
- Build responsive layouts

Example:

```
Header
↓
Employee Details
↓
Related Courses
↓
Dashboard
```

---

#### Q4. What problem do Dynamic Forms solve?

**Dynamic Forms** solve the problem of showing too many fields to every user.

They allow:

- Show fields only when needed
- Conditional visibility
- Better page performance
- Less scrolling

Example:

Without Dynamic Forms:

```
Show all 50 fields
```

With Dynamic Forms:

```
Show Certification fields only if Certified = TRUE
```

Result:\
Cleaner and smarter UI.

---

#### Q5. Design UI for Employee Learning System

##### Page Layout

Employee Layout:

```
Employee Information
Enrollment Details
Certification Section
Related Courses
Activity History
```

Course Layout:

```
Course Details
Pricing
Approval Status
Enrollments
```

---

##### Record Types

Employee Record Types:

| Record Type |
| --- |
| Internal Employee |
| External Contractor |

Course Record Types:

| Record Type |
| --- |
| Technical |
| Leadership |
| Soft Skills |

Purpose:\
Different processes and picklists.

---

##### Dynamic Forms

Visibility Rules:

```
Show Certification Section
IF
Is_Certified = TRUE
```

```
Show Approval Details
IF
Cost > ₹25,000
```

Benefits:

- Cleaner UI
- Personalized experience

---

##### Global Actions

Create quick actions:

| Action | Purpose |
| --- | --- |
| New Enrollment | Create enrollment |
| Add Course | Create course |
| Submit Approval | Start approval |
| Raise Issue | Create support case |

Placement:

```
Global Header
↓
+ New Enrollment
+ Raise Issue
```

Final UI Design:

```
Record Type
↓
Page Layout
↓
Dynamic Forms
↓
Global Actions
↓
Better User Experience
```

This design gives employees, managers, and HR a clean and scalable Employee Learning System UI. ✅

