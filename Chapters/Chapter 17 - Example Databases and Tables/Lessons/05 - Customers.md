---
lesson_id: C17-L05
chapter: 17
lesson: 5
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C17-L05: Customers

## Textbook excerpt

Customers

 Id   FName      LName      Email                        PhoneNumber     PreferredContact

 1    William    Jones      william.jones@example.com    3347927472      PHONE

 2    David      Miller     dmiller@example.net          2137921892      EMAIL

 3    Richard    Davis      richard0123@example.com      NULL            EMAIL



SQL statements to create the table:

 CREATE TABLE Customers (
     Id INT NOT NULL AUTO_INCREMENT,
     FName VARCHAR(35) NOT NULL,
     LName VARCHAR(35) NOT NULL,
     Email varchar(100) NOT NULL,
     PhoneNumber VARCHAR(11),
     PreferredContact VARCHAR(5) NOT NULL,
     PRIMARY KEY(Id)
 );

 INSERT INTO Customers
     ([Id], [FName], [LName], [Email], [PhoneNumber], [PreferredContact])
 VALUES
     (1, 'William', 'Jones', 'william.jones@example.com', '3347927472', 'PHONE'),
     (2, 'David', 'Miller', 'dmiller@example.net', '2137921892', 'EMAIL'),
     (3, 'Richard', 'Davis', 'richard0123@example.com', NULL, 'EMAIL')
 ;

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
