---
chapter: 2
textbook_lesson: C02-L02
status: in_progress
date_started: 2026-10-13
sql_target: Microsoft SQL Server 2012
record_fidelity: teaching summary and exact submitted SQL
assessment_status: first_attempt_8_of_10_correction_pending
---

# Chapter 2 — Lesson 2: DROP COLUMN

**Status:** IN PROGRESS — first coding attempt graded **8/10**; correction pending.

## Textbook material and provenance

- [Source lesson (unchanged)](02%20-%20Drop%20Column.md)
- [Full Chapter 2 reference](../CHAPTER.md)

The book gives:

```sql
ALTER TABLE Employees
DROP COLUMN salary;
```

It explains that this removes the entire `salary` column **and its values**, not just individual values in rows. Its next subsection teaches `DROP CONSTRAINT` and cautions that constraints attached to the column may need removal first. The latter will be covered separately.

## Teaching demonstration (new in this conversation)

In an illustrative hospital `NURSES` table, the now-unused column `OLD_PAGER` can be removed with:

```sql
ALTER TABLE NURSES
DROP COLUMN OLD_PAGER;
```

This changes the table schema and discards that column's values in all rows, while other columns and their values remain. Unlike `ADD`, dropping a column is destructive. For real databases verify dependencies and preserve required data beforehand. The statement is illustrated here, **not executed**.

## Coding challenge — first attempt assessed

> The existing `DOCTORS` table includes an obsolete `OLD_EXTENSION` column. Write one SQL Server 2012 statement to remove that column entirely, preserving the other columns. Use `ALTER TABLE` and `DROP COLUMN`.

### User's submitted SQL (verbatim, 2026-10-13)

```sql
ALTER TABLE  DOCTORS
DROP COLUMN OLD_EXTENTION;
```

### Line-by-line grade: 8/10

- `ALTER TABLE  DOCTORS`: Correct table and command. Double space is harmless.
- `DROP COLUMN`: Correct operation for removing a whole column.
- `OLD_EXTENTION`: **Incorrect identifier**. The exercise explicitly names `OLD_EXTENSION`, with an **S** in EXTENSION. `OLD_EXTENTION` names a different column; if it does not exist, SQL Server cannot drop it.
- `;`: Correct terminator.

**Important distinction:** The submitted statement is syntactically well-formed T-SQL but does **not** fulfill the named-column requirement. The exercise has not been run against an actual SQL Server instance.

**Correct query demonstrated by assistant:**

```sql
ALTER TABLE DOCTORS
DROP COLUMN OLD_EXTENSION;
```

### Correction practice

The student is invited to resubmit the statement spelling `OLD_EXTENSION` exactly, rather than advancing prematurely. **No corrected user submission exists yet.**

**Chapter mastery:** Chapter 2 is in progress; 85% pass threshold applies to the final chapter exam.
