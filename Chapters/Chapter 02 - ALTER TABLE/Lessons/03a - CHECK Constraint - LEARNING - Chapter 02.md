---
chapter: 2
textbook_lesson: C02-L03
topic: CHECK constraint
status: in_progress
date_started: 2026-10-13
sql_target: Microsoft SQL Server 2012
assessment_status: awaiting_student_submission
record_fidelity: teaching summary, practice prompt exact; no user code yet
---

# Chapter 2 — Lesson 3a: CHECK Constraint

## Source-derived point

The textbook's [Add Constraint section](03%20-%20Add%20Constraint.md) lists `CHECK` as one of the types of constraints and describes it as limiting the ranges of values that can be placed in a column. The source **does not supply a CHECK constraint command example in Chapter 2**. The T-SQL demonstrations below are instructor-created to explain the source's topic in SQL Server 2012.

## SQL Server 2012 teaching

A `DEFAULT` supplies a value when an INSERT omits that column. A `CHECK` restricts the values that can be accepted, according to its logical condition.

Instructor-created example (re-adding the age constraint dropped in an earlier practice):

```sql
ALTER TABLE DOCTORS
ADD CONSTRAINT CK_DOCTORS_AGE CHECK (AGE >= 18);
```

This checks new/modified data against the age threshold. SQL Server normally validates existing data on adding a CHECK constraint, too; pre-existing violating values can make the command fail. It does not remove the AGE column or automatically change age values.

## Coding challenge — awaiting submission

> Assume `DOCTORS` has an existing `SALARY INT` column and no `CK_DOCTORS_SALARY` constraint. Write one SQL Server 2012 statement that adds a CHECK constraint named `CK_DOCTORS_SALARY` to require `SALARY >= 0`. Do not add a new column or drop anything. Assume existing rows comply with this rule.

**Student answer:** Pending.

**Grade:** Pending. The Chapter 2 final exam is separate and still pending (85% passing threshold).
