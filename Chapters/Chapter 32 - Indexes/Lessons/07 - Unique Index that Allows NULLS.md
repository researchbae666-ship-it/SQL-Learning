---
lesson_id: C32-L07
chapter: 32
lesson: 7
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C32-L07: Unique Index that Allows NULLS

## Textbook excerpt

Unique Index that Allows NULLS

 CREATE UNIQUE INDEX idx_license_id
    ON Person(DrivingLicenseID) WHERE DrivingLicenseID IS NOT NULL
 GO


This schema allows for a 0..1 relationship - people can have zero or one driving licenses and each
license can only belong to one person

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
