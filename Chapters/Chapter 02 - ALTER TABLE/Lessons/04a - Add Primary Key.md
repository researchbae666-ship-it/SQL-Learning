---
lesson_id: C02-L04a
chapter: 2
lesson: "4a"
status: planned
source: ../CHAPTER.md
sql_target: Microsoft SQL Server 2012 (original syntax needs adaptation)
---

# C02-L04a: Add Primary Key

## Original textbook excerpt (Chapter 2)

Add Primary Key

```sql
ALTER TABLE EMPLOYEES ADD pk_EmployeeID PRIMARY KEY (ID)
```

This will add a Primary key to the table Employees on the field ID. Including more than one column name in the parentheses along with ID will create a Composite Primary Key. When adding more than one column, the column names must be separated by commas.

```sql
ALTER TABLE EMPLOYEES ADD pk_EmployeeID PRIMARY KEY (ID, FName)
```

## SQL Server 2012 compatibility note

The original book examples above should **not** be copied verbatim into Microsoft SQL Server 2012. For a named PRIMARY KEY constraint, the supported syntax is:

```sql
ALTER TABLE EMPLOYEES
ADD CONSTRAINT pk_EmployeeID PRIMARY KEY (ID);
```

For a composite key, likewise:

```sql
ALTER TABLE EMPLOYEES
ADD CONSTRAINT pk_EmployeeID PRIMARY KEY (ID, FName);
```

The column(s) must be non-NULL and the key values (or key combinations) unique; an existing primary key or incompatible dependencies can block the operation. The textbook excerpt is retained unchanged above; the corrective Microsoft SQL Server 2012 syntax is supplemental instruction.

See [live learning record](04a%20-%20Add%20Primary%20Key%20-%20LEARNING%20-%20Chapter%2002.md).
