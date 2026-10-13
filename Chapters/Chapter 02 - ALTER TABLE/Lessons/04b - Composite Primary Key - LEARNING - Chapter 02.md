---
chapter: 2
textbook_lesson: C02-L04a
topic: composite_primary_key
status: completed
date_started: 2026-10-13
sql_target: Microsoft SQL Server 2012
assessment_status: passed_10_of_10
record_fidelity: textbook-grounded concept, instructor-authored example, verbatim learner SQL and real grading
---

# Chapter 2 — Composite Primary Key

**Status: COMPLETED** — composite primary key challenge PASSED **10/10**.

## What the original textbook says

The *Add Primary Key* section of Chapter 2 says that including multiple comma-separated column names within the primary key definition forms a **Composite Primary Key**. The original example is:

```sql
ALTER TABLE EMPLOYEES ADD pk_EmployeeID PRIMARY KEY (ID, FName)
```

Source: [archived source lesson, unmodified](04a%20-%20Add%20Primary%20Key.md). This particular named-constraint syntax does **not** run verbatim in Microsoft SQL Server 2012 because it omits `CONSTRAINT`.

## Instructor-authored SQL Server 2012 teaching

A composite key uses a **combination** of columns as the row identifier. Each column alone can repeat, but the complete pair cannot. All columns in a PRIMARY KEY are required to be non-NULL.

Medical-domain sample rows:

| PATIENTID | VISITNUMBER | Meaning |
|---|---|---|
| 101 | 1 | Patient 101, first visit |
| 101 | 2 | Patient 101, second visit |
| 102 | 1 | Patient 102, first visit |

`PATIENTID` repeats and `VISITNUMBER` repeats. The `(PATIENTID, VISITNUMBER)` pair does not.

A SQL Server 2012 example, **not from the book**:

```sql
ALTER TABLE PATIENT_VISITS
ADD CONSTRAINT PK_PATIENT_VISITS
PRIMARY KEY (PATIENTID, VISITNUMBER);
```

Assumptions: `PATIENT_VISITS` exists, both columns are NOT NULL, all existing pairs are unique, no existing PRIMARY KEY, and no incompatible dependencies.

## Coding challenge — assessed and passed

> Existing table `COURSE_ENROLLMENTS` already has `STUDENTID INT NOT NULL` and `COURSEID INT NOT NULL`. Each ID may repeat separately, but no existing row shares the same pair. There is no primary key yet. Add a composite PRIMARY KEY named `PK_COURSE_ENROLLMENTS` on `(STUDENTID, COURSEID)` in a single SQL Server 2012 `ALTER TABLE` statement.

### Exact student submission — 2026-10-13

```sql
ALTER TABLE COURSE_ENROLLMENTS
ADD CONSTRAINT PK_Course_Enrollments PRIMARY KEY (STUDENTID, COURSEID);
```

### Line-by-line assessment: **10/10 — PASS**

| Submitted SQL | Grade | Explanation |
|---|---|---|
| `ALTER TABLE COURSE_ENROLLMENTS` | Correct | Targets the existing table. |
| `ADD CONSTRAINT` | Correct | SQL Server 2012 named-constraint syntax. |
| `PK_Course_Enrollments` | Correct under usual case-insensitive SQL Server identifier resolution | The requested constraint was named `PK_COURSE_ENROLLMENTS`; letters match but capitalization differs. Preserve consistent casing in real projects; case-sensitive database collations can make identifier case significant. |
| `PRIMARY KEY (STUDENTID, COURSEID)` | Correct | Uses the combination of both existing NOT NULL columns to enforce unique pairs. |
| `;` | Correct | Valid statement terminator. |

**Outcome:** PASS 10/10 on first attempt. Assumptions: table and columns exist, neither column is nullable, existing combinations are unique, table has no primary key, constraints and permissions permit operation. The query was reviewed for correct T-SQL; **no actual SQL Server database was executed**.

**Next:** Review Chapter 2's mixed `ADD` example combining `NOT NULL DEFAULT GETDATE()` with a nullable `DATE` column, then the six constraint types before the final 85%-pass chapter exam.

**After challenge:** check the remaining Chapter 2 source items, including the mixed `ADD` column example with `NOT NULL DEFAULT GETDATE()` and `DATE NULL`, and the textbook's constraint-type list, before issuing the 85%-threshold final chapter mastery exam.
