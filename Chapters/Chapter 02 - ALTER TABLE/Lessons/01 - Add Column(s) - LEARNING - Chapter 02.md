---
chapter: 2
textbook_lesson: C02-L01
status: in_progress
date_started: 2026-10-13
sql_target: Microsoft SQL Server 2012
record_fidelity: teaching summary and verbatim student SQL submission
assessment_status: single_column_10_of_10_and_multiple_columns_10_of_10
---

# Chapter 2 — Lesson 1: Add a new column with ALTER TABLE

**Status: COMPLETED for C02-L01 — single-column and multiple-column exercises both PASSED (10/10).**

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

## Coding challenge — graded 10/10

> Your existing DOCTORS table has DOCTORID, DOCTORNAME, and AGE. Add a new column called SPECIALTY, with datatype VARCHAR(60), allowing NULL values. Write one SQL Server 2012 command. Do not create a new table.

**Expected skill:** `ALTER TABLE ... ADD ... VARCHAR(60) NULL`.

## Student submission

**Verbatim user SQL submission (2026-10-13):**

```sql
ALTER TABLE DOCTORS
ADD SPECIALTY VARCHAR(60) NULL;
```


## Feedback and corrections

**Score: 10/10 — correct.** The query is valid SQL Server 2012 T-SQL if `DOCTORS` exists and `SPECIALTY` does not yet exist. This is syntax review, not a claim the statement was actually executed on a database.

| Submitted code | Grade and feedback |
|---|---|
| `ALTER TABLE DOCTORS` | Correctly chooses an existing table. |
| `ADD SPECIALTY` | Correctly adds the named column. |
| `VARCHAR(60)` | Correct datatype and limit. |
| `NULL;` | Allows nulls and ends the statement correctly. |

**Additional explanation:** Existing DOCTORS rows are retained. Their new nullable SPECIALTY column begins with NULL if the command is executed successfully. The SQL Server default for column nullability can be configuration-dependent, so explicit `NULL` avoids ambiguity.

## Follow-up instruction — adding multiple columns in one ALTER TABLE

The chapter's original multi-column example adds `StartingDate DATE NOT NULL DEFAULT GETDATE()` and `DateOfBirth DATE NULL` to Employees. This introduces the pattern of one `ADD` followed by multiple comma-separated column definitions. Detailed default-constraint behavior can be studied later.

**Teaching demonstration:**

```sql
ALTER TABLE NURSES
ADD WARD VARCHAR(50) NULL,
    FLOORNUMBER INT NULL;
```

Each definition has its own column name, datatype and nullability. The comma separates definitions; use one final semicolon.

**Second coding challenge — PASSED (10/10):** On an existing `DOCTORS` table, add **two new columns in one ALTER TABLE statement**:
- `DEPARTMENT VARCHAR(40) NULL`
- `ROOMNUMBER INT NULL`

### Student's original SQL (verbatim, 2026-10-13)

```sql
ALTER TABLE DOCTORS
ADD DEPARTMENT VARCHAR(40) NULL,
ROOMNUMBER INT NULL;
```

### Assistant's line-by-line assessment

**Score: 10/10. Correct for SQL Server 2012.** It is a valid statement, assuming the table exists and neither named column already exists, and assuming no schema restrictions block the operation. Syntax was reviewed; no SQL Server instance was executed.

| Submitted line | Grade | Explanation |
|---|---|---|
| `ALTER TABLE DOCTORS` | Correct | Targets the existing table. |
| `ADD DEPARTMENT VARCHAR(40) NULL,` | Correct | Names the first new nullable text column; comma separates column definitions. |
| `ROOMNUMBER INT NULL;` | Correct | Names second new nullable integer column; semicolon ends one statement. |

**Additional assistant feedback:** Adding both columns with one `ADD` is correct. The second column's indentation is optional, not an error. Existing rows would be retained and the two newly added nullable columns would initially be `NULL` if executed.

**Outcome:** Both C02-L01 exercises (single column and multiple columns) passed at 10/10. Moved on to textbook C02-L02, Drop Column.

## Mastery

**Lesson C02-L01 completed:** single-column and multi-column addition both assessed at 10/10. Chapter 2 overall is still in progress and has not yet been tested or certified. The chapter exam is after the chapter's topics are taught and practiced. Passing threshold remains 85%.

**Fidelity:** This is a faithful learning-session summary plus the precise exercise specification; it is not represented as an unabridged verbatim export of ChatGPT's message.
