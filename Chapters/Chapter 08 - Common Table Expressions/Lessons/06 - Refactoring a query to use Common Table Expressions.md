---
lesson_id: C08-L06
chapter: 8
lesson: 6
status: planned
source: ../CHAPTER.md
sql_target: Microsoft SQL Server 2012 (compatibility not yet reviewed)
---

# C08-L06: Refactoring a query to use Common Table Expressions

**Chapter:** 8 · **Lesson:** 6 of 6 · **Status:** Planned (historical progress not yet reconciled)

## Textbook material

The following excerpt is preserved from this chapter's archived textbook text. The source uses multiple SQL dialects; validate syntax for SQL Server 2012 before exercises.

Refactoring a query to use Common Table Expressions

Suppose we want to get all product categories with total sales greater than 20.

Here is a query without Common Table Expressions:

 SELECT category.description, sum(product.price) as total_sales
 FROM sale
 LEFT JOIN product on sale.product_id = product.id
 LEFT JOIN category on product.category_id = category.id
 GROUP BY category.id, category.description
 HAVING sum(product.price) > 20


And an equivalent query using Common Table Expressions:

 WITH all_sales AS (
   SELECT product.price, category.id as category_id, category.description as
 category_description
   FROM sale
   LEFT JOIN product on sale.product_id = product.id
   LEFT JOIN category on product.category_id = category.id
 )
 , sales_by_category AS (
   SELECT category_description, sum(price) as total_sales
   FROM all_sales
   GROUP BY category_id, category_description
 )
 SELECT * from sales_by_category WHERE total_sales > 20



Example of a complex SQL with Common Table Expression

Suppose we want to query the "cheapest products" from the "top categories".

Here is an example of query using Common Table Expressions




 -- all_sales: just a simple SELECT with all the needed JOINS
 WITH all_sales AS (
   SELECT
   product.price as product_price,
   category.id as category_id,
   category.description as category_description
   FROM sale
   LEFT JOIN product on sale.product_id = product.id
   LEFT JOIN category on product.category_id = category.id
 )
 -- Group by category
 , sales_by_category AS (
   SELECT category_id, category_description,
   sum(product_price) as total_sales
   FROM all_sales
   GROUP BY category_id, category_description
 )
 -- Filtering total_sales > 20
 , top_categories AS (
   SELECT * from sales_by_category WHERE total_sales > 20
 )
 -- all_products: just a simple SELECT with all the needed JOINS
 , all_products AS (
   SELECT
   product.id as product_id,
   product.description as product_description,
   product.price as product_price,
   category.id as category_id,
   category.description as category_description
   FROM product
   LEFT JOIN category on product.category_id = category.id
 )
 -- Order by product price
 , cheapest_products AS (
   SELECT * from all_products
   ORDER by product_price ASC
 )
 -- Simple inner join
 , cheapest_products_from_top_categories AS (
   SELECT product_description, product_price
   FROM cheapest_products
   INNER JOIN top_categories ON cheapest_products.category_id = top_categories.category_id
 )
 --The main SELECT
 SELECT * from cheapest_products_from_top_categories


Read Common Table Expressions online: https://riptutorial.com/sql/topic/747/common-table-
expressions

## Tutoring session record

*Pending. When this lesson is taught or its past conversation is imported, append the actual exchange, learner's SQL submissions, corrections, feedback, and assessment results faithfully. Do not invent chat content.*
