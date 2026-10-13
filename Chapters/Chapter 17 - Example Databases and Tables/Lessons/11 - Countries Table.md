---
lesson_id: C17-L11
chapter: 17
lesson: 11
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C17-L11: Countries Table

## Textbook excerpt

Countries Table

In this example, we have a Countries table. A table for countries has many uses, especially in
Financial applications involving currencies and exchange rates.

Live example: SQL fiddle

Some Market data software applications like Bloomberg and Reuters require you to give their API
either a 2 or 3 character country code along with the currency code. Hence this example table has
both the 2-character ISO code column and the 3 character ISO3 code columns.



Countries
(view table)

 Id   ISO      ISO3   ISONumeric    CountryName     Capital       ContinentCode     CurrencyCode

 1    AU       AUS    36            Australia       Canberra      OC                AUD

 2    DE       DEU    276           Germany         Berlin        EU                EUR

 2    IN       IND    356           India           New Delhi     AS                INR

 3    LA       LAO    418           Laos            Vientiane     AS                LAK

 4    US       USA    840           United States   Washington    NA                USD


 Id   ISO    ISO3    ISONumeric   CountryName      Capital       ContinentCode    CurrencyCode

 5    ZW     ZWE     716          Zimbabwe         Harare        AF               ZWL

SQL to create the table:

 CREATE TABLE Countries (
     Id INT NOT NULL AUTO_INCREMENT,
     ISO VARCHAR(2) NOT NULL,
     ISO3 VARCHAR(3) NOT NULL,
     ISONumeric INT NOT NULL,
     CountryName VARCHAR(64) NOT NULL,
     Capital VARCHAR(64) NOT NULL,
     ContinentCode VARCHAR(2) NOT NULL,
     CurrencyCode VARCHAR(3) NOT NULL,
     PRIMARY KEY(Id)
 )
 ;

 INSERT INTO Countries
     (ISO, ISO3, ISONumeric, CountryName, Capital, ContinentCode, CurrencyCode)
 VALUES
     ('AU', 'AUS', 36, 'Australia', 'Canberra', 'OC', 'AUD'),
     ('DE', 'DEU', 276, 'Germany', 'Berlin', 'EU', 'EUR'),
     ('IN', 'IND', 356, 'India', 'New Delhi', 'AS', 'INR'),
     ('LA', 'LAO', 418, 'Laos', 'Vientiane', 'AS', 'LAK'),
     ('US', 'USA', 840, 'United States', 'Washington', 'NA', 'USD'),
     ('ZW', 'ZWE', 716, 'Zimbabwe', 'Harare', 'AF', 'ZWL')
 ;


Read Example Databases and Tables online: https://riptutorial.com/sql/topic/280/example-
databases-and-tables

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
