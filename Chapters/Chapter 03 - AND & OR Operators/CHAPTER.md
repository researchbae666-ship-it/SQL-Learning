# Chapter 3: AND & OR Operators

> Source: *SQL*, unofficial Stack Overflow Documentation ebook compiled by Steve Nouri; content credited to Stack Overflow Documentation contributors and licensed CC BY-SA as stated in the original PDF. Extracted from the user-provided 221-page PDF. PDF text formatting is normalized; illustrations remain in the original PDF. See the book credits for chapter contributors.

---

Chapter 3: AND & OR Operators
Syntax
   1. SELECT * FROM table WHERE (condition1) AND (condition2);

   2. SELECT * FROM table WHERE (condition1) OR (condition2);


Examples
AND OR Example

Have a table

 Name     Age     City

 Bob      10      Paris

 Mat      20      Berlin

 Mary     24      Prague

 select Name from table where Age>10 AND City='Prague'


Gives

 Name

 Mary


 select Name from table where Age=10 OR City='Prague'


Gives

 Name

 Bob

 Mary

Read AND & OR Operators online: https://riptutorial.com/sql/topic/1386/and---or-operators
