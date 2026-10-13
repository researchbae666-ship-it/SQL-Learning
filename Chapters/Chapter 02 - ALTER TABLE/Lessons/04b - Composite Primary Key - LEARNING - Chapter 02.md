---
chapter: 2
textbook_lesson: C02-L04a
topic: composite_primary_key
status: in_progress
date_started: 2026-10-13
sql_target: Microsoft SQL Server 2012
assessment_status: awaiting_student_submission
record_fidelity: textbook-grounded concept with clearly marked instructor-authored T-SQL example; user response pending
---

# Chapter 2 — Composite Primary Key

**Status: IN PROGRESS**; exercise not yet submitted.

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

## Coding challenge — awaiting student

> Existing table `COURSE_ENROLLMENTS` already has `STUDENTID INT NOT NULL` and `COURSEID INT NOT NULL`. Each ID may repeat separately, but no existing row shares the same pair. There is no primary key yet. Add a composite PRIMARY KEY named `PK_COURSE_ENROLLMENTS` on `(STUDENTID, COURSEID)` in a single SQL Server 2012 `ALTER TABLE` statement.

**Exact learner SQL:** pending.

**Grade and corrections:** pending.

**After challenge:** check the remaining Chapter 2 source items, including the mixed `ADD` column example with `NOT NULL DEFAULT GETDATE()` and `DATE NULL`, and the textbook's constraint-type list, before issuing the 85%-threshold final chapter mastery exam.
