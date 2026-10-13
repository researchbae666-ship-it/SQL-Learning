# Chapter 46: Sequence

> Source: *SQL*, unofficial Stack Overflow Documentation ebook compiled by Steve Nouri; content credited to Stack Overflow Documentation contributors and licensed CC BY-SA as stated in the original PDF. Extracted from the user-provided 221-page PDF. PDF text formatting is normalized; illustrations remain in the original PDF. See the book credits for chapter contributors.

---

Chapter 46: Sequence
Examples
Create Sequence

  CREATE SEQUENCE orders_seq
  START WITH     1000
  INCREMENT BY   1;


Creates a sequence with a starting value of 1000 which is incremented by 1.

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
