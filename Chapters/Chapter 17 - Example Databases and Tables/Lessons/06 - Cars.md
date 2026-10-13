---
lesson_id: C17-L06
chapter: 17
lesson: 6
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C17-L06: Cars

## Textbook excerpt

Cars

 Id   CustomerId      EmployeeId      Model          Status     Total Cost

 1    1               2               Ford F-150     READY      230

 2    1               2               Ford F-150     READY      200

 3    2               1               Ford Mustang   WAITING    100

 4    3               3               Toyota Prius   WORKING    1254

SQL statements to create the table:

 CREATE TABLE Cars (
     Id INT NOT NULL AUTO_INCREMENT,
     CustomerId INT NOT NULL,
     EmployeeId INT NOT NULL,
     Model varchar(50) NOT NULL,
     Status varchar(25) NOT NULL,
     TotalCost INT NOT NULL,
     PRIMARY KEY(Id),
     FOREIGN KEY (CustomerId) REFERENCES Customers(Id),
     FOREIGN KEY (EmployeeId) REFERENCES Employees(Id)
 );

 INSERT INTO Cars
     ([Id], [CustomerId], [EmployeeId], [Model], [Status], [TotalCost])
 VALUES
     ('1', '1', '2', 'Ford F-150', 'READY', '230'),
     ('2', '1', '2', 'Ford F-150', 'READY', '200'),
     ('3', '2', '1', 'Ford Mustang', 'WAITING', '100'),
     ('4', '3', '3', 'Toyota Prius', 'WORKING', '1254')
 ;

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
