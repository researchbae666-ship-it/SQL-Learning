---
chapter: 2
textbook_lesson: C02-L03
topic: CHECK constraint
status: completed
date_started: 2026-10-13
sql_target: Microsoft SQL Server 2012
assessment_status: passed_10_of_10
record_fidelity: source-grounded teaching summary; exact user code and grading
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

## Coding challenge — PASSED (10/10)

> Assume `DOCTORS` has an existing `SALARY INT` column and no `CK_DOCTORS_SALARY` constraint. Write one SQL Server 2012 statement that adds a CHECK constraint named `CK_DOCTORS_SALARY` to require `SALARY >= 0`. Do not add a new column or drop anything. Assume existing rows comply with this rule.

### User's exact SQL submission (2026-10-13)

```sql
ALTER TABLE DOCTORS
ADD CONSTRAINT CK_DOCTORS_SALARY
CHECK (SALARY >= 0);
```

### Grade: **10/10 — PASS**

| Submitted SQL | Result | Reason |
|---|---|---|
| `ALTER TABLE DOCTORS` | Correct | Specifies the existing DOCTORS table. |
| `ADD CONSTRAINT` | Correct | Introduces a named constraint. |
| `CK_DOCTORS_SALARY` | Correct | Exact required constraint identifier. |
| `CHECK (SALARY >= 0)` | Correct | Forbids negative non-NULL salary values. |
| `;` | Correct | Valid statement terminator. |

**Qualification:** In SQL Server 2012, CHECK constraints accept an UNKNOWN predicate result, so `NULL` is not excluded by `CHECK (SALARY >= 0)` alone. Add `NOT NULL` separately if null must be prohibited. The challenge did not ask to prohibit nulls.

**Execution:** Valid T-SQL syntax assuming DOCTORS and SALARY exist, constraint name is unused, permissions suffice, and existing data satisfies the rule. No live SQL Server execution was performed.

**Outcome:** CHECK practice passed 10/10. Chapter 2 as a whole still awaits further topics and a chapter mastery exam (85% threshold).

## Next teaching step

Proceed to C02-L04, `ALTER COLUMN`: changing an existing column's datatype or nullability.
