## Lesson 7 — Validation Rules (One of the Most Important Admin Skills)

> Admins use validation rules to stop bad data.

### Objective

By the end of this lesson you will know:

1. What Validation Rules are
2. Formula basics
3. Validation syntax
4. Error messages
5. Real business scenarios

---

### 1. What is a Validation Rule?

Validation Rule = Business rule that prevents invalid data from being saved.

Think:

```
User enters data
  ↓
Validation executes
  ↓
Pass → Save
Fail → Error
```

Example:

Rule:

```
Experience cannot be negative
```

Input:

```
-5
```

Result:

❌ Save blocked

---

### 2. Validation Rule Components

Every validation contains:

```
Formula
+
Error Message
+
Error Location
```

Example:

Formula:

```
Experience__c < 0
```

Message:

```
Experience cannot be negative
```

---

### 3. Common Operators

| Operator | Meaning |
| --- | --- |
| = | Equal |
| <> | Not Equal |
| > | Greater |
| < | Less |
| && | AND |
| \|\| | OR |

Functions:

| Function | Purpose |
| --- | --- |
| ISBLANK() | Empty |
| ISPICKVAL() | Picklist |
| TODAY() | Current Date |
| LEN() | Length |

---

### 4. Build Validation Rules for Our Project

#### Rule 1 — Experience Cannot Be Negative

Formula:

```
Experience__c < 0
```

Error:

```
Experience cannot be less than zero.
```

---

#### Rule 2 — Enrollment Date Cannot Be Future

Formula:

```
Enrollment_Date__c > TODAY()
```

Error:

```
Enrollment date cannot be future date.
```

---

#### Rule 3 — Certification Required

Business rule:

If Status = Completed

then Certification Required = TRUE

Assuming:

- `Status__c` → Picklist
- `Certification_Required__c` → Checkbox

Validation Rule Formula:

```
AND(ISPICKVAL(Status__c, "Completed"),NOT(Certification_Required__c))
```

Error Message:

```
Certification is required when status is Completed.
```

Error Location:

```
Field → Certification Required
```

How it works:

- Status = **Completed**
- Certification Required = **Unchecked (FALSE)**

→ ❌ Record cannot be saved

Example:

| Status | Certification Required | Result |
| --- | --- | --- |
| Completed | TRUE | ✅ Save |
| Completed | FALSE | ❌ Error |
| In Progress | FALSE | ✅ Save |

This ensures completed enrollments always have certification marked. ✅

---

### Assignment

#### Q1. What is a Validation Rule?

A **Validation Rule** is a business rule in Salesforce that prevents users from saving invalid or incorrect data.

Flow:

```
User enters data
  ↓
Validation Rule executes
  ↓
Pass → Save
Fail → Show Error
```

Example:\
Experience cannot be negative.

---

#### Q2. If Experience should not exceed 40 years, write formula logic.

Formula:

```
Experience__c > 40
```

Error Message:

```
Experience cannot exceed 40 years.
```

---

#### Q3. Which function checks Picklist values?

Use:

```
ISPICKVAL()
```

Example:

```
ISPICKVAL(Status__c, "Completed")
```

This checks whether the picklist value equals **Completed**.

---

#### Q4. Write formula logic: Enrollment Date should not be blank.

Formula:

```
ISBLANK(Enrollment_Date__c)
```

Error Message:

```
Enrollment Date is required.
```

---

#### Q5. Business Rule: If Course Cost > 0, Category cannot be blank. Formula logic:

```
AND(Cost__c > 0,ISBLANK(TEXT(Category__c)))
```

Error Message:

```
Category is required when Course Cost is greater than zero.
```

Explanation:

- `Cost__c > 0` → Course has a price
- `ISBLANK(TEXT(Category__c))` → Category is empty
- `AND()` → Both conditions true → ❌ Block save

---

