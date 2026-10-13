---
lesson_id: C50-L02
chapter: 50
lesson: 2
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C50-L02: simple injection sample

## Textbook excerpt

simple injection sample

If the SQL statement is constructed like this:

 SQL = "SELECT * FROM Users WHERE username = '" + user + "' AND password ='" + pw + "'";
 db.execute(SQL);


Then a hacker could retrieve your data by giving a password like pw' or '1'='1; the resulting SQL
statement will be:

 SELECT * FROM Users WHERE username = 'somebody' AND password ='pw' or '1'='1'


This one will pass the password check for all rows in the Users table because '1'='1' is always
true.

To prevent this, use SQL parameters:

 SQL = "SELECT * FROM Users WHERE username = ? AND password = ?";
 db.execute(SQL, [user, pw]);




Read SQL Injection online: https://riptutorial.com/sql/topic/3517/sql-injection

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
