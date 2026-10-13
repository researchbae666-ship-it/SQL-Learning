---
lesson_id: C13-L01
chapter: 13
lesson: 1
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C13-L01: DECIMAL and NUMERIC

## Textbook excerpt

Chapter 13: Data Types
Examples
DECIMAL and NUMERIC

Fixed precision and scale decimal numbers. DECIMAL and NUMERIC are functionally equivalent.

Syntax:

 DECIMAL ( precision [ , scale] )
 NUMERIC ( precision [ , scale] )


Examples:

 SELECT CAST(123 AS DECIMAL(5,2)) --returns 123.00
 SELECT CAST(12345.12 AS NUMERIC(10,5)) --returns 12345.12000

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
