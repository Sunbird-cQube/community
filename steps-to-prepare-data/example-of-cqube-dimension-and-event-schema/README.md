---
description: >-
  This page gives an example of cQube Dimension & Event schema for better
  understanding
---

# Example of cQube Dimension & Event Schema

### **Dimension Schema**

**Ex : School Dimension**



This is the data for all schools, clusters, blocks and districts in the state.

**If CSV is being ingested, the file name should be -> school-dimension.data.csv**

\


| #  | Column               | Data type | Description                                         | Validation  |
| -- | -------------------- | --------- | --------------------------------------------------- | ----------- |
| 1  | district\_id         | string    | Unique ID in the district                           | NA          |
| 2  | district\_name       | string    | Name of the district                                | NA          |
| 3  | block\_id            | string    | Unique ID in the block                              | NA          |
| 4  | block\_name          | string    | Name of the block                                   | NA          |
| 5  | cluster\_id          | string    | Unique ID in the cluster                            | NA          |
| 6  | cluster\_name        | string    | Name of the cluster                                 | NA          |
| 7  | school\_id           | string    | Unique ID in the school                             | NA          |
| 8  | school\_name         | string    | Name of the school                                  | NA          |
| 9  | schoolcategory\_name | string    | ID of the school category for the respective school | NA          |
| 10 | grade                | string    | ID of the grade present in the school               | NA          |
| 11 | latitude             | string    | Latitude of the school                              | NA          |
| 12 | longitude            | string    | Longitude of the school                             | NA          |
| 13 | udise\_code          | string    | Unique ID                                           | <p><br></p> |

###

### Event Schemas:

**Ex : Teacher Attendance**



This program entails indicators to monitor compliance and performance of teacher attendance. Following are the reports within this program:

* **Teacher Attendance Compliance:** This report shows the compliance of attendance being marked by teachers.
* **Teacher Attendance Summary:** This report shows the summary of teachers being present in the school (out of the ones marking their attendance).

Following schema will be required to enable the teacher attendance program:

**If CSV is being ingested, the file name should be -> teachersattendance-event.data.csv**

#### **Note: The name for grammar file & event file should be same. e.g: teachersattendance-event.data.csv , teachersattendance-event.grammar.csv**

\
\


| #  | Column Name                  | Data Type | Description                                                            | Validation                              |
| -- | ---------------------------- | --------- | ---------------------------------------------------------------------- | --------------------------------------- |
| 1  | date                         | string    | Date when the data was recorded                                        | <p>DD/MM/YY</p><p>format to be used</p> |
| 2  | district\_id                 | string    | Unique ID of the district as per the dimension table                   | NA                                      |
| 3  | block\_id                    | string    | Unique ID of the block as per the dimension table                      | NA                                      |
| 4  | cluster\_id                  | string    | Unique ID of the cluster as per the dimension table                    | NA                                      |
| 5  | school\_id                   | string    | Unique ID of the school as per the dimension table                     | NA                                      |
| 6  | schoolcategory\_name         | string    | Category\_id which the school ID belongs to as per the dimension table | NA                                      |
| 7  | grade                        | string    | Grade for which the data is being entered                              | NA                                      |
| 8  | total\_teachers              | string    | Total number of teachers                                               | NA                                      |
| 9  | teachers\_attendance\_marked | string    | Total number of teachers whose attendance was marked                   | NA                                      |
| 10 | teachers\_marked\_present    | string    | Total number of teachers who were present                              | NA                                      |

\
\
\


#### NOTE :  Each metric should be part of a separate event table.&#x20;

E.g. In teacher attendance event file, we will have 3 tables: one for total\_teachers, one for teachers\_attendance\_marked & one for teachers\_marked\_present

\
