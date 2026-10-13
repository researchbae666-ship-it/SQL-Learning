---
lesson_id: C17-L08
chapter: 17
lesson: 8
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C17-L08: Authors

## Textbook excerpt

Authors
(view table)

 Id     Name                   Country

 1      J.D. Salinger          USA

 2      F. Scott. Fitzgerald   USA

 3      Jane Austen            UK

 4      Scott Hanselman        USA

 5      Jason N. Gaylord       USA

 6      Pranav Rastogi         India

 7      Todd Miranda           USA

 8      Christian Wenz         USA

SQL to create the table:

 CREATE TABLE Authors (
     Id INT NOT NULL AUTO_INCREMENT,
     Name VARCHAR(70) NOT NULL,
     Country VARCHAR(100) NOT NULL,
     PRIMARY KEY(Id)
 );

 INSERT INTO Authors




     (Name, Country)
 VALUES
     ('J.D. Salinger', 'USA'),
     ('F. Scott. Fitzgerald', 'USA'),
     ('Jane Austen', 'UK'),
     ('Scott Hanselman', 'USA'),
     ('Jason N. Gaylord', 'USA'),
     ('Pranav Rastogi', 'India'),
     ('Todd Miranda', 'USA'),
     ('Christian Wenz', 'USA')
 ;

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
