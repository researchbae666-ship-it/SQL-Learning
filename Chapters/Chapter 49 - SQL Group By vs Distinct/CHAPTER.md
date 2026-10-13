# Chapter 49: SQL Group By vs Distinct

> Source: *SQL*, unofficial Stack Overflow Documentation ebook compiled by Steve Nouri; content credited to Stack Overflow Documentation contributors and licensed CC BY-SA as stated in the original PDF. Extracted from the user-provided 221-page PDF. PDF text formatting is normalized; illustrations remain in the original PDF. See the book credits for chapter contributors.

---

Chapter 49: SQL Group By vs Distinct
Examples
Difference between GROUP BY and DISTINCT

GROUP BY is used in combination with aggregation functions. Consider the following table:


 orderId    userId    storeName     orderValue    orderDate

 1          43        Store A       25            20-03-2016

 2          57        Store B       50            22-03-2016

 3          43        Store A       30            25-03-2016

 4          82        Store C       10            26-03-2016

 5          21        Store A       45            29-03-2016

The query below uses GROUP BY to perform aggregated calculations.

 SELECT
      storeName,
      COUNT(*) AS total_nr_orders,
      COUNT(DISTINCT userId) AS nr_unique_customers,
      AVG(orderValue) AS average_order_value,
      MIN(orderDate) AS first_order,
      MAX(orderDate) AS lastOrder
 FROM
      orders
 GROUP BY
      storeName;


and will return the following information

 storeName       total_nr_orders    nr_unique_customers       average_order_value       first_order       lastOr

                                                                                        20-03-            29-03-
 Store A         3                  2                         33.3
                                                                                        2016              2016

                                                                                        22-03-            22-03-
 Store B         1                  1                         50
                                                                                        2016              2016

                                                                                        26-03-            26-03-
 Store C         1                  1                         10
                                                                                        2016              2016

While DISTINCT is used to list a unique combination of distinct values for the specified columns.



 SELECT DISTINCT
      storeName,
      userId
 FROM
      orders;



 storeName       userId

 Store A         43

 Store B         57

 Store C         82

 Store A         21

Read SQL Group By vs Distinct online: https://riptutorial.com/sql/topic/2499/sql-group-by-vs-
distinct
