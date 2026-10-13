---
chapter: 2
textbook_lesson: C02-L01
status: in_progress
date_started: 2026-10-13
sql_target: Microsoft SQL Server 2012
record_fidelity: faithful lesson summary; exact practice prompt
assessment_status: awaiting_student_submission
---

# Chapter 2 — Lesson 1: Add a new column with ALTER TABLE

**Status: IN PROGRESS — learner practice not yet submitted.**

## Source

- [Textbook lesson: 01 - Add Column(s).md](01%20-%20Add%20Column(s).md).
- [Complete Chapter 2 reference](../CHAPTER.md).

## Teaching in this conversation

The student began Chapter 2 after earning **19.5/20 (97.5%)** and passing the Chapter 1 mastery exam. This session introduced `ALTER TABLE` as changing an *existing* table's structure, contrasted with `CREATE TABLE` for making a new table.

Example used in the teaching:

```sql
ALTER TABLE NURSES
ADD EMAIL VARCHAR(100) NULL;
```

- `ALTER TABLE NURSES`: choose the existing table.
- `ADD EMAIL`: add the EMAIL column.
- `VARCHAR(100)`: store text with a maximum declared length of 100 characters.
- `NULL`: missing values allowed.
- Existing `NURSEID` and `NURSENAME` values remain. On existing rows, the newly added nullable email column has NULL values until populated.

**Textbook scope note:** The source also shows adding multiple columns and `DEFAULT GETDATE()`. That more complex pattern is not yet assessed; the first exercise focuses only on a nullable column.

## Coding challenge — issued, not yet graded

> Your existing DOCTORS table has DOCTORID, DOCTORNAME, and AGE. Add a new column called SPECIALTY, with datatype VARCHAR(60), allowing NULL values. Write one SQL Server 2012 command. Do not create a new table.

**Expected skill:** `ALTER TABLE ... ADD ... VARCHAR(60) NULL`.

## Student submission

*Pending. Do not invent a response or assign a grade before the student's actual submission.*

## Feedback and corrections

*Pending student's SQL.*

## Mastery

**In progress.** Chapter 2 not assessed or certified. The chapter exam is after the chapter's topics are taught and practiced. Passing threshold remains 85%.

**Fidelity:** This is a faithful learning-session summary plus the precise exercise specification; it is not represented as an unabridged verbatim export of ChatGPT's message.
