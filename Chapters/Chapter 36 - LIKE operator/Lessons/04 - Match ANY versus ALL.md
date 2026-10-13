---
lesson_id: C36-L04
chapter: 36
lesson: 4
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C36-L04: Match ANY versus ALL

## Textbook excerpt

Match ANY versus ALL

Match any:
Must match at least one string. In this example the product type must be either 'electronics',
'books', or 'video'.

 SELECT *
 FROM   purchase_table
 WHERE product_type LIKE ANY ('electronics', 'books', 'video');


Match all (must meet all requirements).
In this example both 'united kingdom' and 'london' and 'eastern road' (including variations) must be
matched.

 SELECT *
 FROM   customer_table
 WHERE full_address LIKE ALL ('%united kingdom%', '%london%', '%eastern road%');


Negative selection:
Use ALL to exclude all items.
This example yields all results where the product type is not 'electronics' and not 'books' and not
'video'.

 SELECT *
 FROM   customer_table
 WHERE product_type NOT LIKE ALL ('electronics', 'books', 'video');

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
