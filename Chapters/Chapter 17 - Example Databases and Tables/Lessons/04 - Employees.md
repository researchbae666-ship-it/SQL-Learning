---
lesson_id: C17-L04
chapter: 17
lesson: 4
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C17-L04: Employees

## Textbook excerpt

Employees

 Id   FName         LName      PhoneNumber        ManagerId   DepartmentId   Salary   HireDate

                                                                                      01-01-
 1    James         Smith      1234567890         NULL        1              1000
                                                                                      2002

                                                                                      23-03-
 2    John          Johnson    2468101214         1           1              400
                                                                                      2005

                                                                                      12-05-
 3    Michael       Williams   1357911131         1           2              600
                                                                                      2009

                                                                                      24-07-
 4    Johnathon     Smith      1212121212         2           1              500
                                                                                      2016

SQL statements to create the table:

 CREATE TABLE Employees (
     Id INT NOT NULL AUTO_INCREMENT,
     FName VARCHAR(35) NOT NULL,
     LName VARCHAR(35) NOT NULL,
     PhoneNumber VARCHAR(11),
     ManagerId INT,
     DepartmentId INT NOT NULL,
     Salary INT NOT NULL,
     HireDate DATETIME NOT NULL,
     PRIMARY KEY(Id),
     FOREIGN KEY (ManagerId) REFERENCES Employees(Id),
     FOREIGN KEY (DepartmentId) REFERENCES Departments(Id)
 );

 INSERT INTO Employees
     ([Id], [FName], [LName], [PhoneNumber], [ManagerId], [DepartmentId], [Salary], [HireDate])
 VALUES
     (1, 'James', 'Smith', 1234567890, NULL, 1, 1000, '01-01-2002'),
     (2, 'John', 'Johnson', 2468101214, '1', 1, 400, '23-03-2005'),
     (3, 'Michael', 'Williams', 1357911131, '1', 2, 600, '12-05-2009'),
     (4, 'Johnathon', 'Smith', 1212121212, '2', 1, 500, '24-07-2016')
 ;

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
