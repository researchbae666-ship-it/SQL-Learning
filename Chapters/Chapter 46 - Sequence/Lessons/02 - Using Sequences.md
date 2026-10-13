---
lesson_id: C46-L02
chapter: 46
lesson: 2
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C46-L02: Using Sequences

## Textbook excerpt

Using Sequences

a reference to seq_name.NEXTVAL is used to get the next value in a sequence. A single
statement can only generate a single sequence value. If there are multiple references to
NEXTVAL in a statement, they use will use the same generated number.

NEXTVAL can be used for INSERTS

 INSERT INTO Orders (Order_UID, Customer)
         VALUES (orders_seq.NEXTVAL, 1032);


It can be used for UPDATES

 UPDATE Orders
 SET Order_UID = orders_seq.NEXTVAL
 WHERE Customer = 581;


It can also be used for SELECTS

 SELECT Order_seq.NEXTVAL FROM dual;


Read Sequence online: https://riptutorial.com/sql/topic/1586/sequence

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
