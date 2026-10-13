---
lesson_id: C45-L07
chapter: 45
lesson: 7
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C45-L07: SELECT Using Column Aliases

## Textbook excerpt

SELECT Using Column Aliases

Column aliases are used mainly to shorten code and make column names more readable.

Code becomes shorter as long table names and unnecessary identification of columns (e.g., there
may be 2 IDs in the table, but only one is used in the statement) can be avoided. Along with table
aliases this allows you to use longer descriptive names in your database structure while keeping
queries upon that structure concise.

Furthermore they are sometimes required, for instance in views, in order to name computed
outputs.


All versions of SQL
Aliases can be created in all versions of SQL using double quotes (").

 SELECT
     FName AS "First Name",
     MName AS "Middle Name",
     LName AS "Last Name"
 FROM Employees





Different Versions of SQL
You can use single quotes ('), double quotes (") and square brackets ([]) to create an alias in
Microsoft SQL Server.

 SELECT
     FName AS "First Name",
     MName AS 'Middle Name',
     LName AS [Last Name]
 FROM Employees


Both will result in:

 First Name      Middle Name     Last Name

 James           John            Smith

 John            James           Johnson

 Michael         Marcus          Williams

This statement will return FName and LName columns with a given name (an alias). This is achieved
using the AS operator followed by the alias, or simply writing alias directly after the column name.
This means that the following query has the same outcome as the above.

 SELECT
     FName "First Name",
     MName "Middle Name",
     LName "Last Name"
 FROM Employees



 First Name      Middle Name     Last Name

 James           John            Smith

 John            James           Johnson

 Michael         Marcus          Williams

However, the explicit version (i.e., using the AS operator) is more readable.

If the alias has a single word that is not a reserved word, we can write it without single quotes,
double quotes or brackets:

 SELECT
     FName AS FirstName,
     LName AS LastName
 FROM Employees





 FirstName      LastName

 James          Smith

 John           Johnson

 Michael        Williams

A further variation available in MS SQL Server amongst others is <alias> = <column-or-
calculation>, for instance:


 SELECT FullName = FirstName + ' ' + LastName,
        Addr1    = FullStreetAddress,
        Addr2    = TownName
 FROM CustomerDetails


which is equivalent to:

 SELECT FirstName + ' ' + LastName As FullName
        FullStreetAddress          As Addr1,
        TownName                   As Addr2
 FROM CustomerDetails


Both will result in:

 FullName              Addr1             Addr2

 James Smith           123 AnyStreet     TownVille

 John Johnson          668 MyRoad        Anytown

 Michael Williams      999 High End Dr   Williamsburgh

Some find using = instead of As easier to read, though many recommend against this format,
mainly because it is not standard so not widely supported by all databases. It may cause
confusion with other uses of the = character.


All Versions of SQL
Also, if you need to use reserved words, you can use brackets or quotes to escape:

 SELECT
     FName as "SELECT",
     MName as "FROM",
     LName as "WHERE"
 FROM Employees



Different Versions of SQL



Likewise, you can escape keywords in MSSQL with all different approaches:

 SELECT
     FName AS "SELECT",
     MName AS 'FROM',
     LName AS [WHERE]
 FROM Employees



 SELECT       FROM         WHERE

 James        John         Smith

 John         James        Johnson

 Michael      Marcus       Williams

Also, a column alias may be used any of the final clauses of the same query, such as an ORDER BY:

 SELECT
      FName AS FirstName,
      LName AS LastName
 FROM
      Employees
 ORDER BY
      LastName DESC


However, you may not use

 SELECT
      FName AS SELECT,
      LName AS FROM
 FROM
      Employees
 ORDER BY
      LastName DESC


To create an alias from these reserved words (SELECT and FROM).

This will cause numerous errors on execution.

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
