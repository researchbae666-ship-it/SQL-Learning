---
assessment_id: CH02-MASTERY-2026-10-13
chapter: 2
status: in_progress
date_assigned: 2026-10-13
maximum_points: 40
pass_threshold_percent: 85
pass_threshold_points: 34
sql_target: Microsoft SQL Server 2012
student_answers: 2_of_10_received
grade: pending
---

# Chapter 2 — Cumulative Mastery Examination

**Status: IN PROGRESS; Q1 and Q2 submitted and awaiting deferred grading.** Passing requirement: **34/40 (85%)**.

**Source basis:** [Chapter 2 of the archived SQL textbook](../Chapters/Chapter%2002%20-%20ALTER%20TABLE/CHAPTER.md). This is an instructor-authored assessment, not questions copied from the book. The book contains some syntax for other dialects; the exam uses **SQL Server 2012 T-SQL**, as documented in the [Chapter 2 coverage audit](../Chapters/Chapter%2002%20-%20ALTER%20TABLE/COVERAGE-AUDIT.md).

## Instructions

- Questions are independent hypotheticals; no query must actually be executed.
- Assume stated tables, columns, absence of conflicting names/constraints, adequate permissions, and compatible existing rows.
- Give complete T-SQL for coding questions.
- Each question is worth 4 points, for a total of 40.
- We grade the actual submitted answer to each item; do not claim the exam passed before grading.

## Exam questions — 4 points each

**Q1 — ADD a column.** The existing `NURSES` table needs a nullable `CONTACTEMAIL VARCHAR(80)` column. Add it without recreating the table.

**Q2 — ADD two columns with DEFAULT.** On existing `EMPLOYEES`, add `STARTDATE DATE NOT NULL DEFAULT GETDATE()` and `BIRTHDATE DATE NULL` in one statement.

**Q3 — DROP COLUMN.** Remove the obsolete `FAXNUMBER` column from the existing `CLINICS` table without deleting the table.

**Q4 — DROP CONSTRAINT.** Remove only the existing named constraint `CK_CLINICS_CAPACITY` from `CLINICS`, preserving its columns.

**Q5 — ADD DEFAULT constraint.** `VISITS` has an existing text column `STATUS`. Add a named DEFAULT constraint `DF_VISITS_STATUS` that uses the text `'SCHEDULED'` when STATUS is omitted.

**Q6 — ADD CHECK constraint.** `STAFF` has `HOURS INT`. Add a constraint `CK_STAFF_HOURS` to enforce `HOURS >= 0`.

**Q7 — ALTER COLUMN.** `NURSES.CONTACTEMAIL` already exists as `VARCHAR(80) NULL`. Change it to `VARCHAR(120) NULL` without creating a second column.

**Q8 — Single-column PRIMARY KEY.** `VISITS.VISITID INT NOT NULL` exists, its values are unique, and the table has no primary key. Add a named constraint `PK_VISITS` on `VISITID`.

**Q9 — Composite PRIMARY KEY.** `LAB_ASSIGNMENTS` has `TECHID INT NOT NULL` and `LABID INT NOT NULL`; combinations are unique, with no existing primary key. Add named constraint `PK_LAB_ASSIGNMENTS` over both columns.

**Q10 — Constraints and SQL Server dialect (four subparts, 1 point each).** (a) Which constraint type ensures that `VISITS.PATIENTID` references an existing patient record? (b) Which constraint type prevents duplicate nurse badge numbers without making that column the primary key? (c) Which constraint type prevents NULL values in `DOCTORS.DOCTORNAME`? (d) The book shows `ALTER COLUMN ... DEFAULT (GETDATE())` together. Is this supported as written in SQL Server 2012? If not, name the separate command pattern to add a DEFAULT to an existing column.

## Point rubric

Q1–Q9: 4 points each for correct DDL operation, table/column/constraint names, datatype or predicate requirements, and valid SQL Server 2012 syntax. Award proportional partial credit for otherwise correct SQL with a minor mistake; wrong object names or unsupported syntax lose points. Q10: 1 point for each correct subpart. Final passing score: **34/40 or above**.

## Actual learner responses

### Q1 — Submitted verbatim

```sql
ALTER TABLE NURSES 
ADD CONTACTEMAIL VARCHAR(80) NULL ;
```

### Q2 — Submitted verbatim

```sql
ALTER TABLE EMPLOYEES
ADD 
    STARTDATE DATE NOT NULL CONSTRAINT DF_EMPLOYEES_STARTDATE DEFAULT GETDATE(),
    BIRTHDATE DATE NULL;
```

**Questions Q3–Q10:** Awaiting submission. **All grades are deferred until exam completion.**

## Grading and chapter certification

*Await submission.* Record each question's score and explanation, then update the Chapter 2 index, coverage audit, and repository progress tracker **only if the actual final score meets 85%**; do not overwrite original textbook content.
