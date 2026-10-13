---
lesson_id: C64-L01
chapter: 64
lesson: 1
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C64-L01: Query from XML Data Type

## Textbook excerpt

Chapter 64: XML
Examples
Query from XML Data Type

 DECLARE @xmlIN XML = '<TableData>
 <aaa Main="First">
   <row name="a" value="1" />
   <row name="b" value="2" />
   <row name="c" value="3" />
 </aaa>
 <aaa Main="Second">
   <row name="a" value="3" />
   <row name="b" value="4" />
   <row name="c" value="5" />
 </aaa>
 <aaa Main="Third">
   <row name="a" value="10" />
   <row name="b" value="20" />
   <row name="c" value="30" />
 </aaa>
 </TableData>'

 SELECT t.col.value('../@Main', 'varchar(10)') [Header],
 t.col.value('@name', 'VARCHAR(25)') [name],
 t.col.value('@value', 'VARCHAR(25)') [Value]
 FROM    @xmlIn.nodes('//TableData/aaa/row') AS t (col)


Results

 Header     name     Value
 First       a         1
 First       b         2
 First       c         3
 Second      a         3
 Second      b         4
 Second      c         5
 Third       a         10
 Third       b         20
 Third       c         30


Read XML online: https://riptutorial.com/sql/topic/4421/xml

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
