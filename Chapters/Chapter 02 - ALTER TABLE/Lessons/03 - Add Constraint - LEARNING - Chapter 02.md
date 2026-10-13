---
chapter: 2
textbook_lesson: C02-L03
status: in_progress
date_started: 2026-10-13
sql_target: Microsoft SQL Server 2012
assessment_status: DEFAULT_passed_third_attempt_10_of_10_CHECK_pending
record_fidelity: source-grounded lesson summary plus exact user SQL and grading
---

# Chapter 2 — Lesson 3: ADD CONSTRAINT (DEFAULT)

**Status:** DEFAULT constraint subskill **PASSED** on third attempt (10/10); chapter lesson remains in progress for other constraint types.

## Source excerpt

The textbook's Add Constraint example adds a default on an existing `Salary` column:

```sql
ALTER TABLE Employees
ADD CONSTRAINT DefaultSalary DEFAULT ((100)) FOR [Salary]
```

The chapter identifies PRIMARY KEY, FOREIGN KEY, NOT NULL, UNIQUE, DEFAULT and CHECK as types of constraints. Source: [original Chapter 2 textbook lesson](03%20-%20Add%20Constraint.md).

## Teaching in the current conversation

A constraint defines a rule or default for table data. An `ADD CONSTRAINT` statement applies the named rule to an existing table. The first exercise focuses on a **DEFAULT** constraint; other constraint types will be taught separately.

SQL Server 2012 example from our practice domain:

```sql
ALTER TABLE NURSES
ADD CONSTRAINT DF_NURSES_SHIFT DEFAULT ('DAY') FOR SHIFT;
```

Here `SHIFT` is an existing text column. This provides 'DAY' for future inserted rows when SHIFT isn't explicitly supplied. A default doesn't rewrite existing SHIFT values.

## Coding challenge

> Assume the existing `DOCTORS` table already has a column `SHIFT VARCHAR(20) NULL`. Add a named DEFAULT constraint `DF_DOCTORS_SHIFT` so that future inserted doctors receive `'DAY'` in SHIFT when no SHIFT value is supplied. Do not recreate the table or add the SHIFT column. Use one `ALTER TABLE ... ADD CONSTRAINT ... DEFAULT ... FOR ...` SQL Server 2012 statement.

## Student's original submission — 2026-10-13 (verbatim)

```sql
ALTER TABLE DOCTORS
ADD CONSTRAINT DF_DOCTORS_SHIFT DEFAULT ((DAY)) FOR [SHIFT];
```

## First-attempt assessment: **8/10** — correction required

| Part | Grade | Feedback |
|---|---|---|
| `ALTER TABLE DOCTORS` | Correct | Specifies the intended existing table. |
| `ADD CONSTRAINT DF_DOCTORS_SHIFT` | Correct | Names the DEFAULT constraint properly. |
| `DEFAULT ((DAY))` | Incorrect | `DAY` is not quoted; the challenge requires the text literal `'DAY'`. Parentheses do not turn an unquoted identifier/token into text. |
| `FOR [SHIFT];` | Correct | Specifies the existing target column, with valid SQL Server brackets. |

This is a **syntax and requirement review**, not execution in a live SQL Server 2012 database. The supplied statement does not specify the required string default.

**Corrected example shown by assistant (not yet submitted by student):**

```sql
ALTER TABLE DOCTORS
ADD CONSTRAINT DF_DOCTORS_SHIFT
DEFAULT ('DAY') FOR [SHIFT];
```

`DEFAULT (('DAY'))` is also valid for the text literal. A DEFAULT applies when an INSERT omits the column; it does not rewrite pre-existing rows.

## Second attempt (user's exact SQL, 2026-10-13)

The student submitted this correction after receiving feedback to put quotes around the text literal `'DAY'`:

```sql
ALTER TABLE DOCTORS
ADD CONTRAINT DF_DOCTORS_SHIFT DEFAILT ('DAY') FOR [SHIFT];
```

### Second-attempt assessment: **6/10** — not yet passed

| SQL fragment | Outcome | Explanation |
|---|---|---|
| `ALTER TABLE DOCTORS` | Correct | Table target specified correctly. |
| `ADD CONTRAINT` | **Incorrect** | The keyword must be spelled `CONSTRAINT`, with an S. |
| `DF_DOCTORS_SHIFT` | Correct | Exact required constraint identifier. |
| `DEFAILT ('DAY')` | **Incorrect keyword** | Must be `DEFAULT ('DAY')`. The student successfully corrected the missing string quotes, but misspelled DEFAULT. |
| `FOR [SHIFT];` | Correct | Correct existing target column; valid bracket quoting and statement terminator. |

**Scoring rubric for this attempt:** two independently misspelled mandatory SQL keywords, minus 2 points each from 10 = **6/10**. The statement would not parse in SQL Server, so it has not created a default constraint. Syntax assessed only; no database execution was performed.

**Correct syntax shown previously by assistant (not submitted successfully yet):**

```sql
ALTER TABLE DOCTORS
ADD CONSTRAINT DF_DOCTORS_SHIFT DEFAULT ('DAY') FOR [SHIFT];
```

## Third attempt — 2026-10-13 (exact user SQL)

```sql
ALTER TABLE DOCTORS
ADD CONSTRAINT DF_DOCTORS_SHIFT DEFAULT ('DAY') FOR [SHIFT];
```

### Third-attempt assessment: **10/10 — PASSED**

| Fragment | Feedback |
|---|---|
| `ALTER TABLE DOCTORS` | Correct existing table target. |
| `ADD CONSTRAINT` | Correct keyword spelling, unlike the second attempt. |
| `DF_DOCTORS_SHIFT` | Exact required named DEFAULT constraint. |
| `DEFAULT ('DAY')` | Correct keyword and correctly quoted string literal. |
| `FOR [SHIFT];` | Correct target column and semicolon; SQL Server brackets valid. |

**Assumptions:** `DOCTORS` and `SHIFT` exist, the constraint name is not already in use, and the user has adequate permissions. This is a **review of T-SQL syntax only**, not execution against a live database.

**Progress across attempts:** First 8/10 (unquoted DAY), second 6/10 (keyword spelling mistakes), third **10/10** (all corrected). The DEFAULT subskill is passed; the full Chapter 2 mastery examination is **not yet attempted** (required threshold 85%).

## Next concept

The book also lists CHECK among the types of constraints. We will next study how a CHECK constraint restricts allowed column values, using the SQL Server 2012 syntax `ADD CONSTRAINT ... CHECK (...)`.

The original book names CHECK as a constraint type but does **not** give a full CHECK syntax example in Chapter 2; our exercises for it are instructor-authored T-SQL examples grounded in that named topic. See [separate CHECK learning record](03a%20-%20CHECK%20Constraint%20-%20LEARNING%20-%20Chapter%2002.md).
