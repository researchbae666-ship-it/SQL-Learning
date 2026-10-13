---
lesson_id: C36-L01
chapter: 36
lesson: 1
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C36-L01: Match open-ended pattern

## Textbook excerpt

Chapter 36: LIKE operator
Syntax
      • Wild Card with % : SELECT * FROM [table] WHERE [column_name] Like '%Value%'

        Wild Card with _ : SELECT * FROM [table] WHERE [column_name] Like 'V_n%'

        Wild Card with [charlist] : SELECT * FROM [table] WHERE [column_name] Like
        'V[abc]n%'


Remarks
LIKE condition in WHERE clause is used to search for column values that matches the given
pattern. Patterns are formed using following two wildcard characters

      • % (Percentage Symbol) - Used for representing zero or more characters
      • _ (Underscore) - Used for representing a single character


Examples
Match open-ended pattern

The % wildcard appended to the beginning or end (or both) of a string will allow 0 or more of any
character before the beginning or after the end of the pattern to match.

Using '%' in the middle will allow 0 or more characters between the two parts of the pattern to
match.

We are going to use this Employees Table:

 Id     FName    LName       PhoneNumber      ManagerId     DepartmentId     Salary    Hire_date

                                                                                       23-03-
 1      John     Johnson     2468101214       1             1                400
                                                                                       2005

                                                                                       11-01-
 2      Sophie   Amudsen     2479100211       1             1                400
                                                                                       2010

                                                                                       06-08-
 3      Ronny    Smith       2462544026       2             1                600
                                                                                       2015

                                                                                       23-03-
 4      Jon      Sanchez     2454124602       1             1                400
                                                                                       2005

 5      Hilde    Knag        2468021911       2             1                800       01-01-



 Id   FName      LName     PhoneNumber      ManagerId     DepartmentId   Salary   Hire_date

                                                                                  2000

Following statement matches for all records having FName containing string 'on' from Employees
Table.

 SELECT * FROM Employees WHERE FName LIKE '%on%';



 Id   FName      LName     PhoneNumber     ManagerId      DepartmentId   Salary   Hire_date

                                                                                  06-08-
 3    Ronny      Smith     2462544026      2              1              600
                                                                                  2015

                                                                                  23-03-
 4    Jon        Sanchez   2454124602      1              1              400
                                                                                  2005

Following statement matches all records having PhoneNumber starting with string '246' from
Employees.

 SELECT * FROM Employees WHERE PhoneNumber LIKE '246%';



 Id   FName      LName     PhoneNumber     ManagerId      DepartmentId   Salary   Hire_date

                                                                                  23-03-
 1    John       Johnson   2468101214      1              1              400
                                                                                  2005

                                                                                  06-08-
 3    Ronny      Smith     2462544026      2              1              600
                                                                                  2015

                                                                                  01-01-
 5    Hilde      Knag      2468021911      2              1              800
                                                                                  2000

Following statement matches all records having PhoneNumber ending with string '11' from
Employees.

 SELECT * FROM Employees WHERE PhoneNumber LIKE '%11'



 Id   FName      LName     PhoneNumber      ManagerId     DepartmentId   Salary   Hire_date

                                                                                  11-01-
 2    Sophie     Amudsen   2479100211       1             1              400
                                                                                  2010

                                                                                  01-01-
 5    Hilde      Knag      2468021911       2             1              800
                                                                                  2000

All records where Fname 3rd character is 'n' from Employees.



 SELECT * FROM Employees WHERE FName LIKE '__n%';


(two underscores are used before 'n' to skip first 2 characters)

 Id   FName      LName      PhoneNumber       ManagerId      DepartmentId      Salary   Hire_date

                                                                                        06-08-
 3    Ronny      Smith      2462544026        2              1                 600
                                                                                        2015

                                                                                        23-03-
 4    Jon        Sanchez    2454124602        1              1                 400
                                                                                        2005

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
