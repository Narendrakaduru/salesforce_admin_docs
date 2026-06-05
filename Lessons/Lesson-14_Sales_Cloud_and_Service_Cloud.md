## Lesson 14 — Sales Cloud & Service Cloud

### Objective

By the end of this lesson you will:

1. Understand Sales Cloud and Service Cloud
2. Learn how companies manage sales processes in Salesforce
3. Understand customer support workflows
4. Learn Lead → Opportunity lifecycle
5. Learn Case Management
6. Understand Queues and Assignment Rules
7. Apply these concepts to our Employee Learning System project

---

### 1. What is Sales Cloud?

Sales Cloud is Salesforce's business application used to manage the complete **sales lifecycle**, from finding potential customers to closing business deals.

Main goals:

```
Acquire Customer
↓
Build Relationship
↓
Close Deal
↓
Generate Revenue
```

Sales Cloud helps companies:

- Track customers
- Manage sales pipeline
- Increase conversion rates
- Forecast future revenue
- Automate sales activities

Typical users:

| Role | Responsibility |
| --- | --- |
| Sales Representative | Engage with customers |
| Account Executive | Close deals |
| Sales Manager | Forecast revenue |
| Leadership | Monitor business |

---

### 2. Core Sales Cloud Objects

Sales Cloud revolves around several important objects.

| Object | Purpose |
| --- | --- |
| Lead | Potential customer |
| Account | Company/Organization |
| Contact | Individual person |
| Opportunity | Sales deal |
| Task | Action item |
| Event | Meeting |

Relationship:

```
Lead
↓
Account
↓
Contact
↓
Opportunity
```

---

### 3. Lead Management

#### What is a Lead?

Lead represents someone who may become a future customer.

Lead does not mean confirmed business.

Examples:

- Website registrations
- Marketing campaigns
- Referrals
- Webinar attendees
- Manual outreach

Example:

| Field | Value |
| --- | --- |
| Name | Rahul |
| Company | ABC Corp |
| Interest | Salesforce Training |
| Source | Website |

Stored as:

```
Lead
```

---

#### Lead Lifecycle

```
New
↓
Contacted
↓
Working
↓
Qualified
↓
Converted
```

Meaning:

| Status | Meaning |
| --- | --- |
| New | Just created |
| Contacted | Initial communication |
| Working | Under evaluation |
| Qualified | Potential customer |
| Converted | Converted into business |

---

#### Lead Qualification (Very Important)

Sales teams qualify leads before investing effort.

Common method:

BANT

| Criteria | Meaning |
| --- | --- |
| Budget | Can customer afford? |
| Authority | Can they decide? |
| Need | Do they require solution? |
| Timeline | When will they buy? |

Example:

Customer says:

```
Budget Approved
Need Immediate Implementation
```

Lead becomes qualified.

---

### 4. Lead Conversion (Very Important)

Lead conversion transforms potential business into actual business records.

Conversion creates:

```
Lead
↓
Convert
↓
Account
+
Contact
+
Opportunity
```

---

Example:

Before:

| Object | Value |
| --- | --- |
| Lead | ABC Corp |

After Conversion:

| Object | Value |
| --- | --- |
| Account | ABC Corp |
| Contact | Rahul |
| Opportunity | Salesforce Training Deal |

---

#### What gets created?

##### Account

Represents company.

Example:

```
ABC Corp
```

---

##### Contact

Represents person.

Example:

```
Rahul
HR Manager
```

---

##### Opportunity

Represents deal.

Example:

```
Corporate Training
₹500000
```

---

### 5. Account Management

Account represents organization-level information.

Examples:

- Amazon
- Infosys
- Microsoft

Stores:

- Company details
- Contacts
- Opportunities
- Revenue

Relationship:

```
Account
↓
Multiple Contacts
↓
Multiple Opportunities
```

---

### 6. Contact Management

Contact represents an individual.

Example:

| Field | Example |
| --- | --- |
| Name | Rahul |
| Role | HR Manager |
| Email | rahul@abc.com |

Relationship:

```
Account
↓
Contacts
```

Example:

ABC Corp

Contacts:

```
Rahul
Priya
Amit
```

---

### 7. Opportunity Management

Opportunity represents revenue generation.

Tracks:

- Sales stages
- Amount
- Closing probability

Example:

```
Corporate Training
₹250000
```

---

#### Opportunity Lifecycle

```
Prospecting
↓
Qualification
↓
Proposal
↓
Negotiation
↓
Closed Won
OR
Closed Lost
```

---

Opportunity Fields:

| Field | Example |
| --- | --- |
| Amount | ₹250000 |
| Stage | Proposal |
| Probability | 70% |
| Close Date | 30-Jun |

---

Example:

```
ABC Corp
↓
Training Package
↓
Negotiation
↓
Closed Won
```

---

### 8. Activities (Task & Event)

Sales activities track communication.

---

#### Task

Action to complete.

Examples:

- Call customer
- Send quotation
- Follow-up

---

#### Event

Scheduled interaction.

Examples:

- Product Demo
- Client Meeting

---

Process:

```
Lead
↓
Task
↓
Meeting
↓
Opportunity
```

---

### 9. Forecasting

Forecasting predicts future revenue.

Example:

| Metric | Value |
| --- | --- |
| Sales Target | ₹2 Crores |
| Forecast | ₹1.7 Crores |

Forecast uses:

- Opportunities
- Probability
- Sales stages

Purpose:

- Planning
- Budgeting
- Performance monitoring

---

### 10. What is Service Cloud?

Service Cloud helps organizations manage support operations.

Goal:

```
Issue
↓
Resolution
↓
Customer Satisfaction
```

Teams:

- Support Agents
- Service Managers
- Escalation Teams

Core Object:

```
Case
```

---

### 11. Case Management

#### What is a Case?

Case represents support issue or request.

Examples:

- Login Issue
- Training Access Problem
- Payment Failure

---

Case Fields:

| Field | Example |
| --- | --- |
| Subject | Login Failed |
| Status | New |
| Priority | High |
| Owner | Support Queue |

---

#### Case Lifecycle

```
New
↓
Assigned
↓
Working
↓
Escalated
↓
Resolved
↓
Closed
```

---

Example:

Employee:

```
Cannot Access Course
↓
Case Created
↓
Assigned
↓
Resolved
```

---

### 12. Queues

Queue provides shared ownership.

Instead of assigning directly.

Example:

```
Training Support Queue
```

Process:

```
Case
↓
Queue
↓
Agent Picks
```

Benefits:

- Better workload management
- Faster response
- Shared responsibility

---

### 13. Assignment Rules

Assignment Rules automatically assign records.

Examples:

Case:

```
Priority = High
↓
Assign Senior Agent
```

Lead:

```
Source = Website
↓
Assign Sales Team
```

Process:

```
Record Created
↓
Evaluate Rules
↓
Assign Owner
```

---

### 14. Escalation Rules

Escalation moves unresolved work.

Example:

```
Case Open > 24 Hours
↓
Escalate
↓
Manager
```

Purpose:

- Faster resolution
- SLA compliance

---

### 15. Service Console

Service Console is a support workspace.

Contains:

- Cases
- Customer details
- Activity history
- Knowledge Articles

Benefits:

- Single workspace
- Faster issue handling

---

### Mini Project

Employee Learning System Mapping

| Salesforce Concept | Project |
| --- | --- |
| Lead | Training Request |
| Opportunity | Enrollment |
| Account | Department |
| Contact | Employee |
| Case | Learning Issue |
| Queue | HR Queue |

End-to-End:

```
Training Request
↓
Approval
↓
Enrollment
↓
Certification
↓
Support Case
↓
Resolution
```

---

### Knowledge Check

#### Q1. What is Sales Cloud?

**Sales Cloud** is a Salesforce application used to manage the complete sales process from finding potential customers to closing deals.

Main features:

- Lead Management
- Account Management
- Contact Management
- Opportunity Tracking
- Reports & Dashboards
- Sales Automation

Flow:

```
Lead
↓
Qualified
↓
Opportunity
↓
Closed Won / Lost
```

---

#### Q2. Difference between Lead and Opportunity?

| Lead | Opportunity |
| --- | --- |
| Potential customer | Qualified business deal |
| Early stage | Later sales stage |
| Limited information | Detailed sales information |
| Can be converted | Used to track revenue |

Example:

Lead:

```
Employee interested in training
```

Opportunity:

```
Employee approved for ₹30,000 training
```

Think:

- **Lead → Interest**
- **Opportunity → Revenue/Deal**

---

#### Q3. Explain Lead Conversion.

**Lead Conversion** is the process of converting a qualified lead into business records.

Typically Salesforce creates:

```
Lead
↓
Convert
↓
Account
+
Contact
+
Opportunity (optional)
```

Example:
Employee training inquiry becomes:

- Account → Company
- Contact → Employee
- Opportunity → Training purchase

Lead becomes read-only after conversion.

---

#### Q4. What is a Case?

A **Case** is a record used to track customer, employee, or support issues until resolution.

Cases help manage:

- Questions
- Complaints
- Requests
- Support tickets

Example:

```
Issue:
Unable to access training course
↓
Create Case
↓
Assign
↓
Resolve
```

---

#### Q5. Design: Employee raises a learning issue. Explain the complete flow.

**Case Lifecycle:**

```
New
↓
Assigned
↓
In Progress
↓
Waiting for Employee
↓
Resolved
↓
Closed
```

Meaning:

- New → Case created
- Assigned → Team receives
- In Progress → Investigation
- Waiting → Need employee input
- Resolved → Solution provided
- Closed → Completed

---

### Queue

Queue Name:

```
Learning Support Queue
```

Purpose:

- Holds unassigned learning cases
- Support team picks work
- Balances workload

Members:

- Training Team
- HR Support
- Learning Admin

Flow:

```
Employee
↓
Case Created
↓
Learning Queue
↓
Agent Picks
```

---

### Assignment Rule

Rule:

```
IF
Case Type = Learning Issue
THEN
Assign → Learning Support Queue
```

Additional Example:

```
Priority = High
↓
Assign → HR Manager
```

Final Design:

| Component | Configuration |
| --- | --- |
| Object | Case |
| Lifecycle | New → Assigned → Resolved |
| Queue | Learning Support |
| Assignment Rule | Auto-route learning issues |

This creates an automated support process for employee learning requests. ✅

---

