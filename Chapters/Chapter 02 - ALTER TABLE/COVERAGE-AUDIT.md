# Chapter 2 — Source-coverage audit (SQL Server 2012)

**Source of truth:** [CHAPTER.md](CHAPTER.md), from the user-provided Stack Overflow Documentation PDF. This checklist covers the chapter's content, *not* later chapters or features inferred from the SQL dialect.

**State after the 2026-10-13 single-column primary key challenge.** Chapter 2 is **not** certified; its final mastery exam requires at least 85%.

| Original Chapter 2 section | Status | Evidence / action |
|---|---|---|
| Introduction to ALTER TABLE | Studied | Existing table structure can be modified |
| Add Column(s), single nullable column | Passed, 10/10 | `SPECIALTY VARCHAR(60) NULL` challenge |
| Add Column(s), multiple nullable columns | Passed, 10/10 | `DEPARTMENT, ROOMNUMBER` challenge |
| Add Column(s), NOT NULL DEFAULT current date + nullable DATE example | **Needs focused review** | Original `StartingDate date NOT NULL DEFAULT GetDate(), DateOfBirth date NULL` example has not been directly tested |
| Drop Column | Passed correction, 10/10 | Original attempt 8/10 corrected |
| Drop Constraint | Passed, 10/10 | `CK_DOCTORS_AGE` |
| Add Constraint: DEFAULT | Passed correction, 10/10 | `DF_DOCTORS_SHIFT DEFAULT ('DAY')` |
| Types of constraints: PRIMARY KEY, FOREIGN KEY, NOT NULL, UNIQUE, DEFAULT, CHECK | **Needs complete verbal check** | DEFAULT and CHECK practiced; primary key practiced; remaining category definitions not separately confirmed |
| Add Constraint: CHECK (instructor extension) | Passed, 10/10 | `CK_DOCTORS_SALARY` |
| Alter Column | Passed correction, 10/10 | `SPECIALTY VARCHAR(100) NULL`; original book syntax with inline DEFAULT does not run in SQL Server 2012 |
| Add Primary Key: single-column | Passed, 10/10 | `PK_PATIENTS PRIMARY KEY (PATIENTID)` |
| Add Primary Key: composite | **Exercise pending** | Original book uses two columns; supplemental T-SQL needs `ADD CONSTRAINT` |

## SQL Server 2012 dialect corrections (not claims about the source text)

1. The book's `ALTER COLUMN ... DEFAULT (GETDATE())` in a single statement is not valid SQL Server 2012 syntax; create a separate DEFAULT constraint if needed.
2. The book's named `ADD pk_EmployeeID PRIMARY KEY (...)` syntax omits SQL Server's `CONSTRAINT` keyword. SQL Server 2012 uses `ADD CONSTRAINT pk_EmployeeID PRIMARY KEY (...)`.
3. Source says foreign keys point to primary keys; SQL Server foreign keys may also target eligible UNIQUE keys, but that is outside this Chapter 2 overview.

After composite-key practice, finish the two explicit source gaps above, then give a cumulative Chapter 2 assessment. Do not mark chapter completed based solely on lesson practice.
