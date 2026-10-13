# Chapter 55: Table Design

> Source: *SQL*, unofficial Stack Overflow Documentation ebook compiled by Steve Nouri; content credited to Stack Overflow Documentation contributors and licensed CC BY-SA as stated in the original PDF. Extracted from the user-provided 221-page PDF. PDF text formatting is normalized; illustrations remain in the original PDF. See the book credits for chapter contributors.

---

Chapter 55: Table Design
Remarks
The Open University (1999) Relational Database Systems: Block 2 Relational Theory, Milton
Keynes, The Open University.


Examples
Properties of a well designed table.

A true relational database must go beyond throwing data into a few tables and writing some SQL
statements to pull that data out.
At best a badly designed table structure will slow the execution of queries and could make it
impossible for the database to function as intended.

A database table should not be considered as just another table; it has to follow a set of rules to
be considered truly relational. Academically it is referred to as a 'relation' to make the distinction.

The five rules of a relational table are:

     1. Each value is atomic; the value in each field in each row must be a single value.
     2. Each field contains values that are of the same data type.
     3. Each field heading has a unique name.
     4. Each row in the table must have at least one value that makes it unique amongst the other
        records in the table.
     5. The order of the rows and columns has no significance.

A table conforming to the five rules:

 Id     Name     DOB           Manager

 1      Fred     11/02/1971    3

 2      Fred     11/02/1971    3

 3      Sue      08/07/1975    2

      • Rule 1: Each value is atomic. Id, Name, DOB and Manager only contain a single value.
      • Rule 2: Id contains only integers, Name contains text (we could add that it's text of four
        characters or less), DOB contains dates of a valid type and Manager contains integers (we could
        add that corresponds to a Primary Key field in a managers table).
      • Rule 3: Id, Name, DOB and Manager are unique heading names within the table.
      • Rule 4: The inclusion of the Id field ensures that each record is distinct from any other record
        within the table.



A badly designed table:

 Id     Name    DOB                         Name

 1      Fred    11/02/1971                  3

 1      Fred    11/02/1971                  3

 3      Sue     Friday the 18th July 1975   2, 1

      • Rule 1: The second name field contains two values - 2 and 1.
      • Rule 2: The DOB field contains dates and text.
      • Rule 3: There's two fields called 'name'.
      • Rule 4: The first and second record are exactly the same.
      • Rule 5: This rule isn't broken.

Read Table Design online: https://riptutorial.com/sql/topic/2515/table-design
