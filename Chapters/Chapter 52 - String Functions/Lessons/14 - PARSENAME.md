---
lesson_id: C52-L14
chapter: 52
lesson: 14
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C52-L14: PARSENAME

## Textbook excerpt

PARSENAME

DATABASE : SQL Server

PARSENAME function returns the specific part of given string(object name). object name may
contains string like object name,owner name, database name and server name.

More details MSDN:PARSENAME

Syntax

 PARSENAME('NameOfStringToParse',PartIndex)


Example

To get object name use part index 1


 SELECT PARSENAME('ServerName.DatabaseName.SchemaName.ObjectName',1) // returns `ObjectName`
 SELECT PARSENAME('[1012-1111].SchoolDatabase.school.Student',1)     // returns `Student`


To get schema name use part index 2

 SELECT PARSENAME('ServerName.DatabaseName.SchemaName.ObjectName',2) // returns `SchemaName`
 SELECT PARSENAME('[1012-1111].SchoolDatabase.school.Student',2)     // returns `school`


To get database name use part index 3

 SELECT PARSENAME('ServerName.DatabaseName.SchemaName.ObjectName',3) // returns `DatabaseName`
 SELECT PARSENAME('[1012-1111].SchoolDatabase.school.Student',3)    // returns `SchoolDatabase`




To get server name use part index 4

 SELECT PARSENAME('ServerName.DatabaseName.SchemaName.ObjectName',4) // returns `ServerName`
 SELECT PARSENAME('[1012-1111].SchoolDatabase.school.Student',4)     // returns `[1012-1111]`


PARSENAME will returns null is specified part is not present in given object name string

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
