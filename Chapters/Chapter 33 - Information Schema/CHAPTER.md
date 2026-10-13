# Chapter 33: Information Schema

> Source: *SQL*, unofficial Stack Overflow Documentation ebook compiled by Steve Nouri; content credited to Stack Overflow Documentation contributors and licensed CC BY-SA as stated in the original PDF. Extracted from the user-provided 221-page PDF. PDF text formatting is normalized; illustrations remain in the original PDF. See the book credits for chapter contributors.

---

Chapter 33: Information Schema
Examples
Basic Information Schema Search

One of the most useful queries for end users of large RDBMS's is a search of an information
schema.

Such a query allows users to rapidly find database tables containing columns of interest, such as
when attempting to relate data from 2 tables indirectly through a third table, without existing
knowledge of which tables may contain keys or other useful columns in common with the target
tables.

Using T-SQL for this example, a database's information schema may be searched as follows:

 SELECT *
 FROM INFORMATION_SCHEMA.COLUMNS
 WHERE COLUMN_NAME LIKE '%Institution%'


The result contains a list of matching columns, their tables' names, and other useful information.

Read Information Schema online: https://riptutorial.com/sql/topic/3151/information-schema
