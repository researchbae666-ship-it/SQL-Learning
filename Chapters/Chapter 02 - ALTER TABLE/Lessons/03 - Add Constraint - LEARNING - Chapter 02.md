---
chapter: 2
textbook_lesson: C02-L03
status: in_progress
date_started: 2026-10-13
sql_target: Microsoft SQL Server 2012
assessment_status: first_attempt_8_of_10_correction_pending
record_fidelity: source-grounded lesson summary plus exact user SQL and grading
---

# Chapter 2 — Lesson 3: ADD CONSTRAINT (DEFAULT)

**Status:** In progress — first attempt graded **8/10**; correction pending.

## Source excerpt

The textbook's Add Constraint example adds a default on an existing `Salary` column:

```sql
ALTER TABLE Employees
ADD CONSTRAINT DefaultSalary DEFAULT ((100)) FOR [Salary]
```

The chapter identifies PRIMARY KEY, FOREIGN KEY, NOT NULL, UNIQUE, DEFAULT and CHECK as types of constraints. Source: [original Chapter 2 textbook lesson](03%20-%20Add%20Constraint.md).

## Teaching in the current conversation

A constraint defines a rule or default for table data. An `ADD CONSTRAINT` statement applies the named rule to an existing table. The first exercise focuses on a **DEFAULT** constraint; other constraint types will be taught separately.

SQL Server 2012 example from our practice domain:

```sql
ALTER TABLE NURSES
ADD CONSTRAINT DF_NURSES_SHIFT DEFAULT ('DAY') FOR SHIFT;
```

Here `SHIFT` is an existing text column. This provides 'DAY' for future inserted rows when SHIFT isn't explicitly supplied. A default doesn't rewrite existing SHIFT values.

## Coding challenge

> Assume the existing `DOCTORS` table already has a column `SHIFT VARCHAR(20) NULL`. Add a named DEFAULT constraint `DF_DOCTORS_SHIFT` so that future inserted doctors receive `'DAY'` in SHIFT when no SHIFT value is supplied. Do not recreate the table or add the SHIFT column. Use one `ALTER TABLE ... ADD CONSTRAINT ... DEFAULT ... FOR ...` SQL Server 2012 statement.

## Student's original submission — 2026-10-13 (verbatim)

```sql
ALTER TABLE DOCTORS
ADD CONSTRAINT DF_DOCTORS_SHIFT DEFAULT ((DAY)) FOR [SHIFT];
```

## First-attempt assessment: **8/10** — correction required

| Part | Grade | Feedback |
|---|---|---|
| `ALTER TABLE DOCTORS` | Correct | Specifies the intended existing table. |
| `ADD CONSTRAINT DF_DOCTORS_SHIFT` | Correct | Names the DEFAULT constraint properly. |
| `DEFAULT ((DAY))` | Incorrect | `DAY` is not quoted; the challenge requires the text literal `'DAY'`. Parentheses do not turn an unquoted identifier/token into text. |
| `FOR [SHIFT];` | Correct | Specifies the existing target column, with valid SQL Server brackets. |

This is a **syntax and requirement review**, not execution in a live SQL Server 2012 database. The supplied statement does not specify the required string default.

**Corrected example shown by assistant (not yet submitted by student):**

```sql
ALTER TABLE DOCTORS
ADD CONSTRAINT DF_DOCTORS_SHIFT
DEFAULT ('DAY') FOR [SHIFT];
```

`DEFAULT (('DAY'))` is also valid for the text literal. A DEFAULT applies when an INSERT omits the column; it does not rewrite pre-existing rows.

**Next step:** Student should resubmit the corrected statement. No retake grade has been assigned. Chapter 2's final chapter mastery exam (85% threshold) remains pending.
