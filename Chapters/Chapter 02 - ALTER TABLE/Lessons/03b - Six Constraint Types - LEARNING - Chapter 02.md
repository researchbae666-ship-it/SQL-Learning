---
chapter: 2
textbook_lesson: C02-L03
topic: six_constraint_types
status: in_progress
date_started: 2026-10-13
sql_target: Microsoft SQL Server 2012
assessment_status: knowledge_checkpoint_pending
record_fidelity: exact textbook definitions identified; instructor clarifications identified separately; learner answers pending
---

# Chapter 2 — Six Constraint Types

**Status:** All six types taught, knowledge-check answers awaiting submission. **Chapter mastery exam has not yet occurred.**

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

**Learner answers:** Pending.

**Scoring:** 6/6 to confirm all six have been distinguished; if fewer, review incorrect type(s) only. This is a preparatory knowledge check **separate from the cumulative Chapter 2 exam**, which requires at least 85%.

## Next step

After the type distinction check is complete, deliver the cumulative SQL Server 2012 Chapter 2 mastery examination (minimum 85%). Do not mark Chapter 2 completed before that assessment is passed.
