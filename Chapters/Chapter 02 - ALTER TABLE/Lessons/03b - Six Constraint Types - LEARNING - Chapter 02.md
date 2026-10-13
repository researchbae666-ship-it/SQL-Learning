---
chapter: 2
textbook_lesson: C02-L03
topic: six_constraint_types
status: completed
date_started: 2026-10-13
sql_target: Microsoft SQL Server 2012
assessment_status: knowledge_checkpoint_passed_6_of_6
record_fidelity: exact textbook definitions identified; instructor clarifications distinguished; actual user answers and grading
---

# Chapter 2 — Six Constraint Types

**Status:** All six types taught and correctly matched **6/6 (100%)**. **Chapter 2 final mastery exam is assigned but not yet submitted or graded.**

## Textbook source (Chapter 2: Add Constraint)

Chapter 2 gives this list:

- **Primary Key** — "prevents a duplicate record in the table".
- **Foreign Key** — "points to a primary key from another table".
- **Not Null** — "prevents null values from being entered into a column".
- **Unique** — "uniquely identifies each record in the table".
- **Default** — "specifies a default value".
- **Check** — "limits the ranges of values that can be placed in a column".

The statements above are faithful to the source, which provides **no example code for all six types** in its constraint-type list. Refer to [unchanged Chapter 2 textbook](../CHAPTER.md).

## Instructor clarifications for SQL Server 2012 (not verbatim textbook language)

| Type | Meaning, with example |
|---|---|
| PRIMARY KEY | One key per table, identifying a row by a unique, non-NULL value or combination of values; PATIENTID |
| FOREIGN KEY | A column/value relationship to a key in another table; VISITS.PATIENTID references PATIENTS.PATIENTID, helping prevent visits for missing patients |
| NOT NULL | The column must contain a value rather than NULL; JOINEDDATE |
| UNIQUE | Prevents repeated values (or combinations) in the constrained column(s); e.g. employee ID card number. Unlike a PRIMARY KEY, a table can have multiple UNIQUE constraints |
| DEFAULT | Supplies a value when an inserted row omits the column; SHIFT defaults to 'DAY' |
| CHECK | Restricts allowed values according to a predicate, e.g. SALARY >= 0 |

**SQL Server-specific nuances:** A FOREIGN KEY can reference an eligible UNIQUE key as well as a PRIMARY KEY, which extends the book's simplified sentence. `NOT NULL` is generally applied in column definitions or via `ALTER COLUMN`, not by writing `ADD CONSTRAINT name NOT NULL`. SQL Server CHECK does not disallow NULL by itself; combine with NOT NULL when required. These are instructor clarifications, not claimed to come from the source.

## Six-item concept check — awaiting learner answers

**Prompt:** State the correct constraint type for each case using the exact names in the Chapter 2 list. Six questions, one point each:

1. Prevent an employee's ID number from appearing twice, and make it the table's main row identifier.
2. Require every doctor to have a name, never NULL.
3. Make an appointment's PATIENTID reference a valid patient from PATIENTS.
4. Give each new patient a default STATUS value of 'ACTIVE' when it isn't supplied.
5. Prevent SALARY values below zero.
6. Prevent two doctors from sharing an EMAIL address, without making EMAIL the table's primary key.

## Actual student responses and grading — 2026-10-13

These are the actual selections submitted by the learner, not reconstructed examples.

| Question | Student's exact answer | Grade | Explanation |
|---|---|---|---|
| 1. Employee ID as main unique row identifier | `PRIMARY KEY` | 1/1 | Identifies each row uniquely; primary-key columns cannot be NULL. |
| 2. Require doctor name, never NULL | `NOT NULL` | 1/1 | Prohibits NULLs in that column. |
| 3. Appointment PATIENTID references patient | `FOREIGN KEY` | 1/1 | Enforces an appropriate relationship to a referenced key. |
| 4. Set STATUS='ACTIVE' if omitted | `DEFAULT` | 1/1 | Supplies a default when an inserted row omits the column. |
| 5. Reject SALARY below zero | `CHECK` | 1/1 | Limits allowed values using a condition. |
| 6. Keep EMAIL unique but not the primary key | `UNIQUE` | 1/1 | Enforces uniqueness without designating a primary key. |

**Score: 6/6 = 100%, PASS.** No mistakes or corrective assignments.

**Assessment scope:** This is a preparatory six-question type-identification check, **not** the Chapter 2 final exam. The final chapter exam is [published here](../../../Assessments/Chapter%2002%20-%20Mastery%20Exam%20-%202026-10-13.md) and is awaiting submission and grading. Its passing threshold is 85%.

**Scoring:** 6/6 to confirm all six have been distinguished; if fewer, review incorrect type(s) only. This is a preparatory knowledge check **separate from the cumulative Chapter 2 exam**, which requires at least 85%.

## Next step

The six-type checkpoint has been passed at 6/6. The final cumulative SQL Server 2012 Chapter 2 mastery examination is now published with 10 questions and 40 points; **Chapter 2 remains in progress** until that exam earns at least 34/40 (85%).
