#### Database ####

There are 7 tables in the database.

|            |                                                                                                                      |
|------------|----------------------------------------------------------------------------------------------------------------------|
|   TABLES   |                                  Brief Description                                                                   |
| INSTRUCTOR | This table has 2 columns: `IID`and `Name`. This is only for instructors from the Course_Offerings Table. The primary |  |            | key is `IID`.                                                                                                        |
| LOCATION   | This table has 2 columns : `LID` and `Location`. This is only for locations from the Course_Meetings Table. The      |  |            | primary key is `LID`.                                                                                                |
| PROGRAM    | This table has 2 columns : `PID` and `Program`. This is only for programs from the Course_Catalog Table. The primary |  |            | key is `PID`.                                                                                                        |
| COURSE_CATALOG |This table has 7 columns : `CatalogID`, `PID`, `Credits`, `Title`, `Prereqs`, `Attributes`, `Description`. The    | |            | primary key is the `CourseID` and the foreign key is the `PID`.                                                      |
| COURSE_MEETINGS | This table has 7 columns : `CMID`, `LID`, `Term`, `CRN`, `Day`, `Start`, `End`. The primary key is the `CMID`   | |            | and the foreign key is the `LID`.                                                                                    |
| COURES_OFFERINGS | This table has 12 columns : `COID`, `CRN`, `Term`, `CatalogID`, `Section`, `Credits`, `Title`, `Meetings`,     |  |            | `IID`,  `Cap`, `Act`, `Rem`. The primary key is `COID` and the foreign keys are `IID` and `CatalogID`.               |



#### Data Warehouse ####
|            |                                                                                                                      |
|------------|----------------------------------------------------------------------------------------------------------------------|
| Tables | Brief Description |
| INSTRUCTOR_WH | This table has 2 columns : `IID` and `Name`. The primary key is `IID`. This is mainly for instructor name. |
| LOCATION_WH | This table has 2 columns : `LID` and `Location`. The primary key is `LID`. This is mainly for locations. |
| MEETINGS_WH | This table has 2 columns : `MID` and `Meetings`. The primary key is `MID`. This is maily for meetings. |
| TOTAL_COURSES_WH | This table has 2 columns : `TCID` and `Total_Courses`. The primary key is `TCID`. This is mainly for displaying| |the amount of times CRNs are used. |
| COURSES_WH | This table has 14 columns. The primary key is `COID`. Please use this SQL query to show the columns: PRAGMA | |table_info(COURSES_WH); . There are a lot of columns. |



# USEFUL QUERIES FOR MORE INFORMATION #

**If you would like to view all of the datatypes for the columns in the tables, please follow this structure. Thank you!**

SQL QUERY:    PRAGMA table_info(<table_name>);

