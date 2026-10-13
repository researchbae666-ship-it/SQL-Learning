# Chapter 62: Views

> Source: *SQL*, unofficial Stack Overflow Documentation ebook compiled by Steve Nouri; content credited to Stack Overflow Documentation contributors and licensed CC BY-SA as stated in the original PDF. Extracted from the user-provided 221-page PDF. PDF text formatting is normalized; illustrations remain in the original PDF. See the book credits for chapter contributors.

---

Chapter 62: Views
Examples
Simple views

A view can filter some rows from the base table or project only some columns from it:

 CREATE VIEW new_employees_details AS
 SELECT E.id, Fname, Salary, Hire_date
 FROM Employees E
 WHERE hire_date > date '2015-01-01';


If you select form the view:

 select * from new_employees_details



 Id   FName          Salary       Hire_date

 4    Johnathon      500          24-07-2016


Complex views

A view can be a really complex query(aggregations, joins, subqueries, etc). Just be sure you add
column names for everything you select:

 Create VIEW dept_income AS
 SELECT d.Name as DepartmentName, sum(e.salary) as TotalSalary
 FROM Employees e
 JOIN Departments d on e.DepartmentId = d.id
 GROUP BY d.Name;


Now you can select from it as from any table:

 SELECT *
 FROM dept_income;



 DepartmentName            TotalSalary

 HR                        1900

 Sales                     600

Read Views online: https://riptutorial.com/sql/topic/766/views
