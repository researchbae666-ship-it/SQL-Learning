---
lesson_id: C52-L02
chapter: 52
lesson: 2
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C52-L02: Concatenate

## Textbook excerpt

Concatenate

In (standard ANSI/ISO) SQL, the operator for string concatenation is ||. This syntax is supported
by all major databases except SQL Server:

 SELECT 'Hello' || 'World' || '!'; --returns HelloWorld!


Many databases support a CONCAT function to join strings:

 SELECT CONCAT('Hello', 'World'); --returns 'HelloWorld'


Some databases support using CONCAT to join more than two strings (Oracle does not):

 SELECT CONCAT('Hello', 'World', '!'); --returns 'HelloWorld!'


In some databases, non-string types must be cast or converted:

 SELECT CONCAT('Foo', CAST(42 AS VARCHAR(5)), 'Bar'); --returns 'Foo42Bar'


Some databases (e.g., Oracle) perform implicit lossless conversions. For example, a CONCAT on a
CLOB and NCLOB yields a NCLOB. A CONCAT on a number and a varchar2 results in a varchar2, etc.:


 SELECT CONCAT(CONCAT('Foo', 42), 'Bar') FROM dual; --returns Foo42Bar


Some databases can use the non-standard + operator (but in most, + works only for numbers):

 SELECT 'Foo' + CAST(42 AS VARCHAR(5)) + 'Bar';


On SQL Server < 2012, where CONCAT is not supported, + is the only way to join strings.

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
