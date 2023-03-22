---
description: >-
  Details out the schemas of events and dimensions for all programs in which
  cQube v5.0 ingests data
---

# cQube Schemas

cQube requires 2 types of schemas for the programs that need to be enabled:

1. [Event Schema](cqube-schemas.md#event-schema)
2. Dimension Schema

## Event Schema

There are 3 state programs available in cQube v5.0:

1. [Student Attendance](cqube-schemas.md#student-attendance)
2. [Teacher Attendance](cqube-schemas.md#teacher-attendance)
3. [Review Meetings](cqube-schemas.md#review-meetings)

### Student Attendance:

This program entails indicators to monitor compliance and performance of student attendance. Following are the reports within this program.

1. **Student Attendance Compliance:** This report shows the compliance of student attendance being marked in the schools. A school is counted as attendance-compliant when attendance of more than 50% of the students in the school is marked on a particular date.&#x20;
2. **Student Attendance Summary:** This report shows the summary of students being present in the schools (out of the ones being marked).

Following schema will be required to enable the student attendance program:

| 1  | date                         | string | Date when the data was recorded                                        | YYYY-MM-DD format to be used          |
| -- | ---------------------------- | ------ | ---------------------------------------------------------------------- | ------------------------------------- |
| 2  | district\_id                 | string | Unique ID of the district as per the dimension table                   | NA                                    |
| 3  | block\_id                    | string | Unique ID of the block as per the dimension table                      | NA                                    |
| 4  | cluster\_id                  | string | Unique ID of the cluster as per the dimension table                    | NA                                    |
| 5  | school\_id                   | string | Unique ID of the school as per the dimension table                     | NA                                    |
| 6  | grade\_state                 | string | Grade for which the data is being entered                              | Restricted to values from 1 to 12     |
| 7  | schoolcategory\_id           | string | Category\_id which the school ID belongs to as per the dimension table | NA                                    |
| 8  | gender                       | string | Gender for which data is being entered                                 | Accepted Values - Male, Female, Other |
| 9  | total\_students              | string | Total number of students                                               | NA                                    |
| 10 | students\_attendance\_marked | string | Total number of students whose attendance was marked                   | NA                                    |
| 11 | students\_marked\_present    | string | Total number of students who were present in the class                 | NA                                    |

[Here](https://docs.google.com/spreadsheets/d/1whs4Oi0ZmUeTgS3e02qjbq7RrzrlotahJI4Vo9wnna0/edit#gid=0) is the upload template for this schema. You can use this template to fill the state data and upload it into cQube. [Here](https://docs.google.com/spreadsheets/d/1o7E0LPTOMVBYe7oTbGY4j\_Ogx2MI6vSsoM-S3WUDRe4/edit#gid=0) is the sample template for this schema to see the kind of data and template in which cQube will accept data.

### Teacher Attendance:

This program entails indicators to monitor compliance and performance of teacher attendance. Following are the reports within this program:

* **Teacher Attendance Compliance:** This report shows the compliance of attendance being marked by teachers.&#x20;
* **Teacher Attendance Summary:** This report shows the summary of teachers being present in the school (out of the ones marking their attendance).

Following schema will be required to enable the teacher attendance program:

| 1  | date                         | string  | Date when the data was recorded                                        | YYYY-MM-DD format to be used      |
| -- | ---------------------------- | ------- | ---------------------------------------------------------------------- | --------------------------------- |
| 2  | district\_id                 | string  | Unique ID of the district as per the dimension table                   | NA                                |
| 3  | block\_id                    | string  | Unique ID of the block as per the dimension table                      | NA                                |
| 4  | cluster\_id                  | string  | Unique ID of the cluster as per the dimension table                    | NA                                |
| 5  | school\_id                   | string  | Unique ID of the school as per the dimension table                     | NA                                |
| 6  | schoolcategory\_id           | string  | Category\_id which the school ID belongs to as per the dimension table | NA                                |
| 7  | grade\_state                 | integer | Grade for which the data is being entered                              | Restricted to values from 1 to 12 |
| 8  | total\_teachers              | integer | Total number of teachers                                               | NA                                |
| 9  | teachers\_attendance\_marked | integer | Total number of teachers whose attendance was marked                   | NA                                |
| 10 | teachers\_marked\_present    | integer | Total number of teachers who were present                              | NA                                |

[Here](https://docs.google.com/spreadsheets/d/1aF9kbA-DiJswb\_5apWnbQU9LRuUEqyYRx3Oc4mbrorY/edit#gid=0) is the upload template for this schema. You can use this template to fill the state data and upload it into cQube. [Here](https://docs.google.com/spreadsheets/d/12KkfH1cokh8PM1toWYuCBgcXr82LMIYAzpN7ktljeOY/edit#gid=0) is the sample template for this schema to see the kind of data and template in which cQube will accept data.

### Review Meetings:

This program entails indicators to monitor compliance of monthly review meetings being conducted at all levels.

Following schema will be required to enable the review meetings program:

1. **For district review meetings:**

| 1 | date               | string | Date of the meeting conducted at the district             | YYYY-MM-DD format to be used |
| - | ------------------ | ------ | --------------------------------------------------------- | ---------------------------- |
| 2 | district\_id       | string | Unique ID of the district as per the dimension table      | NA                           |
| 3 | academicyear\_id   | string | Unique ID of the academic year as per the dimension table | NA                           |
| 4 | meeting\_conducted | string | Whether the meeting is conducted or not                   | 1, 0                         |

2. **For block review meetings:**

| 1 | date               | string | Date of the meeting conducted at the block                | YYYY-MM-DD format to be used |
| - | ------------------ | ------ | --------------------------------------------------------- | ---------------------------- |
| 2 | block\_id          | string | Unique ID of the block as per the dimension table         | NA                           |
| 3 | district\_id       | string | Unique ID of the district as per the dimension table      | NA                           |
| 4 | academicyear\_id   | string | Unique ID of the academic year as per the dimension table | NA                           |
| 5 | meeting\_conducted | string | Whether meeting is conducted or not                       | 1, 0                         |

3. **For cluster review meetings:**

| 1 | date               | string | Date of the meeting conducted at the cluster              | YYYY-MM-DD format to be used |
| - | ------------------ | ------ | --------------------------------------------------------- | ---------------------------- |
| 2 | cluster\_id        | string | Unique ID of the cluster as per the dimension table       | NA                           |
| 3 | block\_id          | string | Unique ID of the block as per the dimension table         | NA                           |
| 4 | district\_id       | string | Unique ID of the district as per the dimension table      | NA                           |
| 5 | academicyear\_id   | string | Unique ID of the academic year as per the dimension table | NA                           |
| 6 | meeting\_conducted | string | Whether meeting is conducted or not                       | 1, 0                         |
