## Lesson 6 — Formula Fields & Roll-Up Summary

> This is where Salesforce becomes powerful.

### Objective

By the end of this lesson:

1. Create Formula Fields
2. Understand Calculated Values
3. Use Cross-Object Formulas
4. Build Roll-Up Summary Fields
5. Use real reporting logic

---

### 1. What is a Formula Field?

Formula Field = A field whose value is automatically calculated.

No data is stored manually.

Think:

```
Input Fields
  ↓
Formula Executes
  ↓
Output Generated
```

Example:

```
Experience = 8
```

Formula:

```
Experience * 12
```

Output:

```
96 months
```

---

### 2. Formula Field Examples

#### Employee Experience in Months

Field:

```
Experience_Months__c
```

Formula:

```
Experience__c * 12
```

---

#### Certification Status

Business Rule:

If Certified → Show Completed

Formula concept:

```
IF(...)
```

Example:

```
IF(Is_Certified__c,"Completed","In Progress")
```

**How IF() works**

Structure:

```
IF(condition,value_if_true,value_if_false)
```

Meaning:

- Check a condition
- If condition = TRUE → return first value
- Otherwise → return second value

**In your example:**

```
IF(Is_Certified__c,"Completed","In Progress")
```

Breakdown:

| Part | Meaning |
| --- | --- |
| `Is_Certified__c` | Checkbox field (TRUE/FALSE) |
| `"Completed"` | Show this if checkbox = TRUE |
| `"In Progress"` | Show this if checkbox = FALSE |

---

#### Course Discount

Fields:

```
Cost__c
Discount__c
```

Formula:

```
Cost__c - (Cost__c * Discount__c / 100)
```

Business Rule:

> Calculate the final course price after applying discount.

Fields:

- `Cost__c` → Currency
- `Discount__c` → Number (Percentage)

**How it works**

Formula structure:

```
Original Cost - Discount Amount
```

Discount Amount:

```
Cost × Discount %
```

Final result:

```
Cost - Discount Amount
```

**Example:**

Course Cost:

```
₹10,000
```

Discount:

```
20
```

Calculation:

```
10000 - (10000 × 20 / 100)
```

Result:

```
₹8,000
```

---

### 3. Cross-Object Formula

Formula can reference parent fields.

Example:

```
Enrollment.Course.Cost
```

Meaning:

```
Enrollment
↓
Read Course Cost
```

Very common.

---

### 4. Roll-Up Summary (Master-Detail Only)

Roll-Up Summary calculates values from child records.

Operations:

- COUNT
- SUM
- MIN
- MAX

Example:

```
Course
↓
Enrollment
```

Count enrollments.

Output:

```
Total Enrollments = 25
```

Example:

```
Employee
↓
Enrollment
```

Roll-Up:

```
Completed Courses
```

Count child records.

---

### Real Project

Employee Dashboard:

```
Employee
├── Total Courses
├── Total Cost
└── Certification Count
```

Most of this comes from Formula + Roll-Up.

---

### Knowledge Check

#### Q1. What is a Formula Field?

A **Formula Field** is a field in Salesforce that automatically calculates and displays a value based on other fields.

Characteristics:

- Read-only
- Auto-updates when source data changes
- No manual input required

Example:

```
Cost__c - (Cost__c * Discount__c / 100)
```

---

#### Q2. Write formula: Convert Experience years into months.

Formula:

```
Experience__c * 12
```

Example:

| Experience | Output |
| --- | --- |
| 2 | 24 Months |
| 5 | 60 Months |

---

#### Q3. Write formula: If Cost > 10000 → return "Premium", else "Standard".

Formula:

```
IF(Cost__c > 10000,"Premium","Standard")
```

Example:

| Cost | Result |
| --- | --- |
| ₹15,000 | Premium |
| ₹8,000 | Standard |

---

#### Q4. Which relationship supports Roll-Up Summary and why?

✅ **Master-Detail Relationship**

Why:\
Because Salesforce allows parent records to automatically calculate values from child records.

Examples:

- Count child records
- Sum values
- Minimum value
- Maximum value

Lookup relationships do not support Roll-Up Summary directly.

---

#### Q5. Scenario: Employee has many Enrollments. Create a Roll-Up Summary requirement to show completed course count.

Design:

| Item | Answer |
| --- | --- |
| Parent Object | Employee |
| Child Object | Enrollment |
| Roll-Up Type | COUNT |
| Filter Condition | Status = Completed |

Requirement:

> Count only enrollment records where Status = Completed and display total on Employee.

Example:

Employee:

```
Narendra
```

Enrollments:

| Course | Status |
| --- | --- |
| Salesforce Admin | Completed |
| DevOps | In Progress |
| ServiceNow | Completed |

Roll-Up Result:

```
Completed Course Count = 2
```

Implementation idea:

```
Employee
 ↓
Fields & Relationships
 ↓
New
 ↓
Roll-Up Summary
 ↓
Summarized Object → Enrollment
 ↓
Roll-Up Type → COUNT
 ↓
Filter → Status = Completed
```

This automatically updates whenever enrollment status changes. ✅

---

