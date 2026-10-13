---
lesson_id: C13-L08
chapter: 13
lesson: 8
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C13-L08: UNIQUEIDENTIFIER

## Textbook excerpt

UNIQUEIDENTIFIER

A 16-byte GUID / UUID.

 DECLARE @GUID UNIQUEIDENTIFIER = NEWID();
 SELECT @GUID -- 'E28B3BD9-9174-41A9-8508-899A78A33540'
 DECLARE @bad_GUID_string VARCHAR(100) = 'E28B3BD9-9174-41A9-8508-899A78A33540_foobarbaz'
 SELECT
     @bad_GUID_string,   -- 'E28B3BD9-9174-41A9-8508-899A78A33540_foobarbaz'
     CONVERT(UNIQUEIDENTIFIER, @bad_GUID_string) -- 'E28B3BD9-9174-41A9-8508-899A78A33540'


Read Data Types online: https://riptutorial.com/sql/topic/1166/data-types

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
