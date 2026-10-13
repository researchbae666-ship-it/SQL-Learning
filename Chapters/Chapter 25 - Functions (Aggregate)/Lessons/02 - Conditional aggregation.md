---
lesson_id: C25-L02
chapter: 25
lesson: 2
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C25-L02: Conditional aggregation

## Textbook excerpt

Conditional aggregation

Payments Table

 Customer       Payment_type      Amount

 Peter          Credit            100

 Peter          Credit            300

 John           Credit            1000

 John           Debit             500

 select customer,
        sum(case when payment_type = 'credit' then amount else 0 end) as credit,
        sum(case when payment_type = 'debit' then amount else 0 end) as debit
 from payments
 group by customer


Result:





 Customer      Credit      Debit

 Peter         400         0

 John          1000        500

 select customer,
        sum(case when payment_type = 'credit' then 1 else 0 end) as credit_transaction_count,
        sum(case when payment_type = 'debit' then 1 else 0 end) as debit_transaction_count
 from payments
 group by customer


Result:

 Customer      credit_transaction_count   debit_transaction_count

 Peter         2                          0

 John          1                          1

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
