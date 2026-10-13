---
lesson_id: C13-L05
chapter: 13
lesson: 5
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C13-L05: BINARY and VARBINARY

## Textbook excerpt

BINARY and VARBINARY

Binary data types of either fixed length or variable length.

Syntax:

 BINARY [ ( n_bytes ) ]
 VARBINARY [ ( n_bytes | max ) ]


n_bytes can be any number from 1 to 8000 bytes. max indicates that the maximum storage space is
2^31-1.

Examples:

 SELECT CAST(12345 AS BINARY(10)) -- 0x00000000000000003039
 SELECT CAST(12345 AS VARBINARY(10)) -- 0x00003039

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
