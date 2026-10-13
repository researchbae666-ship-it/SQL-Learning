---
lesson_id: C52-L01
chapter: 52
lesson: 1
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C52-L01: Trim empty spaces

## Textbook excerpt

Chapter 52: String Functions
Introduction
String functions perform operations on string values and return either numeric or string values.

Using string functions, you can, for example, combine data, extract a substring, compare strings,
or convert a string to all uppercase or lowercase characters.


Syntax
   • CONCAT ( string_value1, string_value2 [, string_valueN ] )
   • LTRIM ( character_expression )
   • RTRIM ( character_expression )
   • SUBSTRING ( expression ,start , length )
   • ASCII ( character_expression )
   • REPLICATE ( string_expression ,integer_expression )
   • REVERSE ( string_expression )
   • UPPER ( character_expression )
   • TRIM ( [ characters FROM ] string )
   • STRING_SPLIT ( string , separator )
   • STUFF ( character_expression , start , length , replaceWith_expression )
   • REPLACE ( string_expression , string_pattern , string_replacement )


Remarks
String functions reference for Transact-SQL / Microsoft

String functions reference for MySQL

String functions reference for PostgreSQL


Examples
Trim empty spaces

Trim is used to remove write-space at the beginning or end of selection

In MSSQL there is no single TRIM()

 SELECT LTRIM(' Hello ') --returns 'Hello '
 SELECT RTRIM(' Hello ') --returns ' Hello'
 SELECT LTRIM(RTRIM(' Hello ')) --returns 'Hello'


MySql and Oracle



 SELECT TRIM('    Hello    ') --returns 'Hello'

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
