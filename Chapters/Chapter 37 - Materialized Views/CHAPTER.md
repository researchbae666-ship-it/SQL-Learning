# Chapter 37: Materialized Views

> Source: *SQL*, unofficial Stack Overflow Documentation ebook compiled by Steve Nouri; content credited to Stack Overflow Documentation contributors and licensed CC BY-SA as stated in the original PDF. Extracted from the user-provided 221-page PDF. PDF text formatting is normalized; illustrations remain in the original PDF. See the book credits for chapter contributors.

---

Chapter 37: Materialized Views
Introduction
A materialized view is a view whose results are physically stored and must be periodically
refreshed in order to remain current. They are therefore useful for storing the results of complex,
long-running queries when realtime results are not required. Materialized views can be created in
Oracle and PostgreSQL. Other database systems offer similar functionality, such as SQL Server's
indexed views or DB2's materialized query tables.


Examples
PostgreSQL example

 CREATE TABLE mytable (number INT);
 INSERT INTO mytable VALUES (1);

 CREATE MATERIALIZED VIEW myview AS SELECT * FROM mytable;

 SELECT * FROM myview;
  number
 --------
       1
 (1 row)

 INSERT INTO mytable VALUES(2);

 SELECT * FROM myview;
  number
 --------
       1
 (1 row)

 REFRESH MATERIALIZED VIEW myview;

 SELECT * FROM myview;
  number
 --------
       1
       2
 (2 rows)


Read Materialized Views online: https://riptutorial.com/sql/topic/8367/materialized-views
