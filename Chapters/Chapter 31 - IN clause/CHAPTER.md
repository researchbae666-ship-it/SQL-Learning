# Chapter 31: IN clause

> Source: *SQL*, unofficial Stack Overflow Documentation ebook compiled by Steve Nouri; content credited to Stack Overflow Documentation contributors and licensed CC BY-SA as stated in the original PDF. Extracted from the user-provided 221-page PDF. PDF text formatting is normalized; illustrations remain in the original PDF. See the book credits for chapter contributors.

---

Chapter 31: IN clause
Examples
Simple IN clause

To get records having any of the given ids

 select *
 from products
 where id in (1,8,3)


The query above is equal to

 select *
 from products
 where id = 1
    or id = 8
    or id = 3



Using IN clause with a subquery

 SELECT *
 FROM customers
 WHERE id IN (
     SELECT DISTINCT customer_id
     FROM orders
 );


The above will give you all the customers that have orders in the system.

Read IN clause online: https://riptutorial.com/sql/topic/3169/in-clause
