---
lesson_id: C38-L02
chapter: 38
lesson: 2
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C38-L02: MySQL: counting users by name

## Textbook excerpt

MySQL: counting users by name

Suppose we want to know how many users have the same name. Let us create table users as
follows:

 create table users(
     id int primary key auto_increment,
     name varchar(8),
     count int,
     unique key name(name)
 );


Now, we just discovered a new user named Joe and would like to take him into account. To
achieve that, we need to determine whether there is an existing row with his name, and if so,



update it to increment count; on the other hand, if there is no existing row, we should create it.

MySQL uses the following syntax : insert … on duplicate key update …. In this case:

 insert into users(name, count)
        values ('Joe', 1)
        on duplicate key update count=count+1;

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
