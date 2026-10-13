---
lesson_id: C61-L04
chapter: 61
lesson: 4
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C61-L04: UPDATE with data from another table

## Textbook excerpt

UPDATE with data from another table

The examples below fill in a PhoneNumber for any Employee who is also a Customer and currently
does not have a phone number set in the Employees Table.

(These examples use the Employees and Customers tables from the Example Databases.)


Standard SQL
Update using a correlated subquery:

 UPDATE
     Employees
 SET PhoneNumber =
     (SELECT
           c.PhoneNumber
      FROM
           Customers c
      WHERE
           c.FName = Employees.FName
           AND c.LName = Employees.LName)
 WHERE Employees.PhoneNumber IS NULL




SQL:2003
Update using MERGE:

 MERGE INTO
     Employees e
 USING
     Customers c
 ON
     e.FName = c.Fname
     AND e.LName = c.LName
     AND e.PhoneNumber IS NULL
 WHEN MATCHED THEN
    UPDATE
       SET PhoneNumber = c.PhoneNumber




SQL Server
Update using INNER JOIN:



 UPDATE
      Employees
 SET
      PhoneNumber = c.PhoneNumber
 FROM
      Employees e
 INNER JOIN Customers c
          ON e.FName = c.FName
          AND e.LName = c.LName
 WHERE
      PhoneNumber IS NULL

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
