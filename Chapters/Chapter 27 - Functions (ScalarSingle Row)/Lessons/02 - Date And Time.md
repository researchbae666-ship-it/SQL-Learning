---
lesson_id: C27-L02
chapter: 27
lesson: 2
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C27-L02: Date And Time

## Textbook excerpt

Date And Time

In SQL, you use date and time data types to store calendar information. These data types include
the time, date, smalldatetime, datetime, datetime2, and datetimeoffset. Each data type has a
specific format.


 Data type         Format

 time              hh:mm:ss[.nnnnnnn]

 date              YYYY-MM-DD

 smalldatetime     YYYY-MM-DD hh:mm:ss

 datetime          YYYY-MM-DD hh:mm:ss[.nnn]

 datetime2         YYYY-MM-DD hh:mm:ss[.nnnnnnn]

 datetimeoffset    YYYY-MM-DD hh:mm:ss[.nnnnnnn] [+/-]hh:mm


The DATENAME function returns the name or value of a specific part of the date.

 SELECT DATENAME (weekday,'2017-01-14') as Datename



 Datename

 Saturday


You use the GETDATE function to determine the current date and time of the computer running the
current SQL instance. This function doesn't include the time zone difference.

 SELECT GETDATE() as Systemdate



 Systemdate

 2017-01-14 11:11:47.7230728


The DATEDIFF function returns the difference between two dates.

In the syntax, datepart is the parameter that specifies which part of the date you want to use to
calculate difference. The datepart can be year, month, week, day, hour, minute, second, or
millisecond. You then specify the start date in the startdate parameter and the end date in the
enddate parameter for which you want to find the difference.

 SELECT SalesOrderID, DATEDIFF(day, OrderDate, ShipDate)
 AS 'Processing time'
 FROM Sales.SalesOrderHeader



 SalesOrderID      Processing time

 43659             7

 43660             7

 43661             7

 43662             7


The DATEADD function enables you to add an interval to part of a specific date.

 SELECT DATEADD (day, 20, '2017-01-14') AS Added20MoreDays



 Added20MoreDays

 2017-02-03 00:00:00.000

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
