---
description: >-
  Details out the schemas of events and dimensions for all programs in which
  cQube Ed V 5.0 ingests data
---

# cQube Schemas

cQube requires 2 types of schemas for the programs that need to be enabled:

1. [Event Schema](cqube-schemas.md#event-schema)
2. [Dimension Schema](cqube-schemas.md#dimension-schema)

## Event Schema

There are 3 state programs available in cQube v5.0 for which the event schema needs to be ingested by the cQube adopter:

1. [Student Attendance](cqube-schemas.md#student-attendance)
2. [Teacher Attendance](cqube-schemas.md#teacher-attendance)
3. [Review Meetings](cqube-schemas.md#review-meetings)

The schemas for national programs (UDISE, PGI, PM POSHAN, NAS, DIKSHA, NISHTHA) can be accessed [here](https://drive.google.com/drive/folders/1z7OVnzUuo17EI4mIokF97rrftbxpL02k?usp=sharing).

### Student Attendance:

This program entails indicators to monitor compliance and performance of student attendance. Following are the reports within this program.

1. **Student Attendance Compliance:** This report shows the compliance of student attendance being marked in the schools. A school is counted as attendance-compliant when attendance of more than 50% of the students in the school is marked on a particular date.&#x20;
2. **Student Attendance Summary:** This report shows the summary of students being present in the schools (out of the ones being marked).

Following schema will be required to enable the student attendance program:

If CSV is being ingested, the file name should be -> _studentsattendance-event.data.csv_

| #  | Column Name                  | Data Type | Description                                                            | Validation                   |
| -- | ---------------------------- | --------- | ---------------------------------------------------------------------- | ---------------------------- |
| 1  | date                         | string    | Date when the data was recorded                                        | YYYY-MM-DD format to be used |
| 2  | district\_id                 | string    | Unique ID of the district as per the dimension table                   | NA                           |
| 3  | block\_id                    | string    | Unique ID of the block as per the dimension table                      | NA                           |
| 4  | cluster\_id                  | string    | Unique ID of the cluster as per the dimension table                    | NA                           |
| 5  | school\_id                   | string    | Unique ID of the school as per the dimension table                     | NA                           |
| 6  | grade                        | string    | Grade for which the data is being entered                              | NA                           |
| 7  | schoolcategory\_id           | string    | Category\_id which the school ID belongs to as per the dimension table | NA                           |
| 8  | gender                       | string    | Gender for which data is being entered                                 | NA                           |
| 9  | total\_students              | string    | Total number of students                                               | NA                           |
| 10 | students\_attendance\_marked | string    | Total number of students whose attendance was marked                   | NA                           |
| 11 | students\_marked\_present    | string    | Total number of students who were present in the class                 | NA                           |

[Here](https://docs.google.com/spreadsheets/d/1whs4Oi0ZmUeTgS3e02qjbq7RrzrlotahJI4Vo9wnna0/edit#gid=0) is the upload template for this schema. You can use this template to fill the state data and upload it into cQube. [Here](https://docs.google.com/spreadsheets/d/1o7E0LPTOMVBYe7oTbGY4j\_Ogx2MI6vSsoM-S3WUDRe4/edit#gid=0) is the sample template for this schema to see the kind of data and template in which cQube will accept data.

### Teacher Attendance:

This program entails indicators to monitor compliance and performance of teacher attendance. Following are the reports within this program:

* **Teacher Attendance Compliance:** This report shows the compliance of attendance being marked by teachers.&#x20;
* **Teacher Attendance Summary:** This report shows the summary of teachers being present in the school (out of the ones marking their attendance).

Following schema will be required to enable the teacher attendance program:

If CSV is being ingested, the file name should be -> _teachersattendance-event.data.csv_

| #  | Column Name                  | Data Type | Description                                                            | Validation                   |
| -- | ---------------------------- | --------- | ---------------------------------------------------------------------- | ---------------------------- |
| 1  | date                         | string    | Date when the data was recorded                                        | YYYY-MM-DD format to be used |
| 2  | district\_id                 | string    | Unique ID of the district as per the dimension table                   | NA                           |
| 3  | block\_id                    | string    | Unique ID of the block as per the dimension table                      | NA                           |
| 4  | cluster\_id                  | string    | Unique ID of the cluster as per the dimension table                    | NA                           |
| 5  | school\_id                   | string    | Unique ID of the school as per the dimension table                     | NA                           |
| 6  | schoolcategory\_id           | string    | Category\_id which the school ID belongs to as per the dimension table | NA                           |
| 7  | grade                        | string    | Grade for which the data is being entered                              | NA                           |
| 8  | total\_teachers              | string    | Total number of teachers                                               | NA                           |
| 9  | teachers\_attendance\_marked | string    | Total number of teachers whose attendance was marked                   | NA                           |
| 10 | teachers\_marked\_present    | string    | Total number of teachers who were present                              | NA                           |

[Here](https://docs.google.com/spreadsheets/d/1LrEnftK8Z2ecDajN0qNIdd3gz1TjeMrdPTzxM35F5jw/edit#gid=0) is the upload template for this schema. You can use this template to fill the state data and upload it into cQube. [Here](https://docs.google.com/spreadsheets/d/1DjG3N11fi3pLN43Qj9t1L6loNDM0LHpBlfFQKK3Wb7w/edit#gid=0) is the sample template for this schema to see the kind of data and template in which cQube will accept data.

### Review Meetings:

This program entails indicators to monitor compliance of monthly review meetings being conducted at all levels.

Following schema will be required to enable the review meetings program:

1. **For district review meetings:**

If CSV is being ingested, the file name should be -> _district-event.data.csv_

| # | Column Name        | Data Type | Description                                               | Validation                   |
| - | ------------------ | --------- | --------------------------------------------------------- | ---------------------------- |
| 1 | date               | string    | Date of the meeting conducted at the district             | YYYY-MM-DD format to be used |
| 2 | district\_id       | string    | Unique ID of the district as per the dimension table      | NA                           |
| 3 | academicyear\_id   | string    | Unique ID of the academic year as per the dimension table | NA                           |
| 4 | meeting\_conducted | string    | Whether the meeting is conducted or not                   | 1, 0                         |

2. **For block review meetings:**

If CSV is being ingested, the file name should be -> _block-event.data.csv_

| # | Column Name        | Data Type | Description                                               | Validation                   |
| - | ------------------ | --------- | --------------------------------------------------------- | ---------------------------- |
| 1 | date               | string    | Date of the meeting conducted at the block                | YYYY-MM-DD format to be used |
| 2 | block\_id          | string    | Unique ID of the block as per the dimension table         | NA                           |
| 3 | district\_id       | string    | Unique ID of the district as per the dimension table      | NA                           |
| 4 | academicyear\_id   | string    | Unique ID of the academic year as per the dimension table | NA                           |
| 5 | meeting\_conducted | string    | Whether meeting is conducted or not                       | 1, 0                         |

3. **For cluster review meetings:**

If CSV is being ingested, the file name should be -> _cluster-event.data.csv_

| # | Column Name        | Data Type | Description                                               | Validation                   |
| - | ------------------ | --------- | --------------------------------------------------------- | ---------------------------- |
| 1 | date               | string    | Date of the meeting conducted at the cluster              | YYYY-MM-DD format to be used |
| 2 | cluster\_id        | string    | Unique ID of the cluster as per the dimension table       | NA                           |
| 3 | block\_id          | string    | Unique ID of the block as per the dimension table         | NA                           |
| 4 | district\_id       | string    | Unique ID of the district as per the dimension table      | NA                           |
| 5 | academicyear\_id   | string    | Unique ID of the academic year as per the dimension table | NA                           |
| 6 | meeting\_conducted | string    | Whether meeting is conducted or not                       | 1, 0                         |

[Here](https://docs.google.com/spreadsheets/d/1Nj77UxNZ45xmPpsiSX0V0qbAKbdLrkokkJQRzXvDoyg/edit#gid=1933044832) is the upload template for this schema. You can use this template to fill the state data and upload it into cQube. [Here](https://docs.google.com/spreadsheets/d/1PUlqh1VCaYNLhBvRbdJIyxqnogmRWiQv3Bkq-e4UhJ0/edit#gid=1933044832) is the sample template for this schema to see the kind of data and template in which cQube will accept data.

## Dimension Schema

For all the state programs, some dimensions (master data) will need to be ingested by the cQube adopter as well.

There are 8 dimensions for which the data needs to be ingested by the cQube adopter in order to get the state programs:

1. [State Dimension](cqube-schemas.md#state-dimension)
2. [District Dimension](cqube-schemas.md#district-dimension)
3. [Block Dimension](cqube-schemas.md#block-dimension)
4. [Cluster Dimension](cqube-schemas.md#cluster-dimension)
5. [School Dimension](cqube-schemas.md#school-dimension)
6. [School Category Dimension](cqube-schemas.md#school-category-dimension)
7. [Grade Dimension](cqube-schemas.md#grade-dimension)
8. [Gender Dimension](cqube-schemas.md#gender-dimension)

### State Dimension:

This is the data for the particular state.

If CSV is being ingested, the file name should be -> _state-dimension.data.csv_

| # | Column Name | Data Type | Description            | Validation |
| - | ----------- | --------- | ---------------------- | ---------- |
| 1 | state\_id   | string    | Unique ID in the table | NA         |
| 2 | state\_name | string    | Name of the state      | NA         |
| 3 | latitude    | string    | Latitude of the state  | NA         |
| 4 | longitude   | string    | Longitude of the state | NA         |

[Here](https://docs.google.com/spreadsheets/d/19TKSpDMO7IyLR5T0YWGrVla5Bc0yO0W9GzYU\_PzJDDg/edit#gid=0) is the upload template for this schema. You can use this template to fill the state data and upload it into cQube. [Here](https://docs.google.com/spreadsheets/d/1Z1mK\_W\_Z9WOdCjA8my7N6F\_uJlHrmftQ18tQvhgcag4/edit#gid=0) is the sample template for this schema to see the kind of data and template in which cQube will accept data.

### District Dimension:

This is the data for all districts in the state.

If CSV is being ingested, the file name should be -> _district-dimension.data.csv_

| # | Column Name    | Data Type | Description               | Validation |
| - | -------------- | --------- | ------------------------- | ---------- |
| 1 | state\_id      | string    | Unique ID in the table    | NA         |
| 2 | state\_name    | string    | Name of the state         | NA         |
| 3 | district\_id   | string    | Unique ID in the district | NA         |
| 4 | district\_name | string    | Name of the district      | NA         |
| 5 | latitude       | string    | Latitude of the district  | NA         |
| 6 | longitude      | string    | Longitude of the district | NA         |

[Here](https://docs.google.com/spreadsheets/d/1KcpgS-yagkyjzN4ZTh6GZGUY8qBpnRHZheERW9KhAxg/edit#gid=0) is the upload template for this schema. You can use this template to fill the state data and upload it into cQube. [Here](https://docs.google.com/spreadsheets/d/1L2Nrj0hUNmMxRpr04GEZ8nJRmR9Pbyxu\_ECS9dyvJh0/edit#gid=0) is the sample template for this schema to see the kind of data and template in which cQube will accept data.

### Block Dimension:

This is the data for all blocks and districts in the state.

If CSV is being ingested, the file name should be -> _block-dimension.data.csv_

| # | Column Name    | Data Type | Description               | Validation |
| - | -------------- | --------- | ------------------------- | ---------- |
| 1 | district\_id   | string    | Unique ID in the district | NA         |
| 2 | district\_name | string    | Name of the district      | NA         |
| 3 | block\_id      | string    | Unique ID in the block    | NA         |
| 4 | block\_name    | string    | Name of the block         | NA         |
| 5 | latitude       | string    | Latitude of the block     | NA         |
| 6 | longitude      | string    | Longitude of the block    | NA         |

[Here](https://docs.google.com/spreadsheets/d/1Z33WQlVc6F1OCe2VE8zAFNk8Thp5qD4BVM9sM0Nd0zU/edit#gid=0) is the upload template for this schema. You can use this template to fill the state data and upload it into cQube. [Here](https://docs.google.com/spreadsheets/d/1R2kS0gjsREK57s7DlVl2ylNDZY9TzcWv\_H\_lHDgbkcQ/edit#gid=0) is the sample template for this schema to see the kind of data and template in which cQube will accept data.

### Cluster Dimension:

This is the data for all clusters, blocks and districts in the state.

If CSV is being ingested, the file name should be -> _cluster-dimension.data.csv_

| # | Column Name    | Data Type | Description               | Validation |
| - | -------------- | --------- | ------------------------- | ---------- |
| 1 | district\_id   | string    | Unique ID in the district | NA         |
| 2 | district\_name | string    | Name of the district      | NA         |
| 3 | block\_id      | string    | Unique ID in the block    | NA         |
| 4 | block\_name    | string    | Name of the block         | NA         |
| 5 | cluster\_id    | string    | Unique ID in the cluster  | NA         |
| 6 | cluster\_name  | string    | Name of the cluster       | NA         |
| 7 | latitude       | string    | Latitude of the cluster   | NA         |
| 8 | longitude      | string    | Longitude of the cluster  | NA         |

[Here](https://docs.google.com/spreadsheets/d/1sI1WXQOYVIxvuwfvqIzFpOwXoY\_Js9w5Dn9rN1zkej0/edit?usp=share\_link) is the upload template for this schema. You can use this template to fill the state data and upload it into cQube. [Here](https://docs.google.com/spreadsheets/d/13LpdBhP2P-VsgEilOMs5enRYei2lII17FUlW7SwYjBc/edit?usp=share\_link) is the sample template for this schema to see the kind of data and template in which cQube will accept data.

### School Dimension:

This is the data for all schools, clusters, blocks and districts in the state.

If CSV is being ingested, the file name should be -> _school-dimension.data.csv_

| #  | Column Name        | Data Type | Description                                         | Validation |
| -- | ------------------ | --------- | --------------------------------------------------- | ---------- |
| 1  | district\_id       | string    | Unique ID in the district                           | NA         |
| 2  | district\_name     | string    | Name of the district                                | NA         |
| 3  | block\_id          | string    | Unique ID in the block                              | NA         |
| 4  | block\_name        | string    | Name of the block                                   | NA         |
| 5  | cluster\_id        | string    | Unique ID in the cluster                            | NA         |
| 6  | cluster\_name      | string    | Name of the cluster                                 | NA         |
| 7  | school\_id         | string    | Unique ID in the school                             | NA         |
| 8  | school\_name       | string    | Name of the school                                  | NA         |
| 9  | schoolcategory\_id | string    | ID of the school category for the respective school | NA         |
| 10 | grade\_id          | string    | ID of the grade present in the school               | NA         |
| 11 | latitude           | string    | Latitude of the school                              | NA         |
| 12 | longitude          | string    | Longitude of the school                             | NA         |

[Here](https://docs.google.com/spreadsheets/d/1q7waS\_pUsmFkwioeto4YcBN3oy-UVMdv5oEZpDnwDU8/edit#gid=0) is the upload template for this schema. You can use this template to fill the state data and upload it into cQube. [Here](https://docs.google.com/spreadsheets/d/1G\_in031-haS4kO2GNFbzaq-c7Dhv6CXuVSXA6nEILG4/edit#gid=0) is the sample template for this schema to see the kind of data and template in which cQube will accept data.

### School Category Dimension:

This is the data for categories of schools present in the state (Eg: Primary, Upper Primary, Secondary, Senior Secondary or any other kind of category).

If CSV is being ingested, the file name should be -> _schoolcategory-dimension.data.csv_

| # | Column Name          | Data Type | Description                                                 | Validation |
| - | -------------------- | --------- | ----------------------------------------------------------- | ---------- |
| 1 | schoolcategory\_id   | string    | Unique ID of the school category                            | NA         |
| 2 | schoolcategory\_name | string    | Name of the school category                                 | NA         |
| 3 | grades               | string    | Array of grades available in the respective school category | NA         |

[Here](https://docs.google.com/spreadsheets/d/1PFPLZbNfDiY7eZX\_7IljNBbUGiyeBJS2kZx4VyREW0Y/edit#gid=0) is the upload template for this schema. You can use this template to fill the state data and upload it into cQube. [Here](https://docs.google.com/spreadsheets/d/17vbEPwLMEHgKhkgJBwCAkGM0xyC4p74ALPAxpefbxWo/edit#gid=0) is the sample template for this schema to see the kind of data and template in which cQube will accept data.

### Grade Dimension:

This is the data for grades present in schools in the state (Eg: 1, 2, 3, 4, 5 or any other grades present in the state).

If CSV is being ingested, the file name should be -> _grade-dimension.data.csv_

| # | Column Name | Data Type | Description                                | Validation |
| - | ----------- | --------- | ------------------------------------------ | ---------- |
| 1 | grade\_id   | string    | Unique ID of the grade                     | NA         |
| 4 | grade       | string    | Grade as per what is followed in the state | NA         |

**Note:** The grade column will consist of the master values from the state data, DIKSHA Data and NAS Data.

[Here](https://docs.google.com/spreadsheets/d/1N3v-rNXVau6YUl5wRI-QLXwM723EVIC7W9EnNgdX6bQ/edit#gid=0) is the upload template for this schema. You can use this template to fill the state data and upload it into cQube. [Here](https://docs.google.com/spreadsheets/d/1hMhOM7a3OY3MnRJrF\_KKQ5ipVjZDmhZhmXH\_Ufgl9NM/edit#gid=0) is the sample template for this schema to see the kind of data and template in which cQube will accept data.

### Gender Dimension:

This is the master data for genders present in the state (Eg: Male, Female, Other).

If CSV is being ingested, the file name should be -> _gender-dimension.data.csv_

| # | Column Name | Data Type | Description             | Validation |
| - | ----------- | --------- | ----------------------- | ---------- |
| 1 | gender\_id  | string    | Unique ID of the gender | NA         |
| 2 | gender      | string    | Name of the gender      | NA         |

[Here](https://docs.google.com/spreadsheets/d/1mjxP6oeBbpdWvB-L4hjdMDk9WMZQ2QeANREkcpxN-jI/edit#gid=0) is the upload template for this schema. You can use this template to fill the state data and upload it into cQube. [Here](https://docs.google.com/spreadsheets/d/1\_lbfGtafwJnA2MJO3A272NhJ-bGLtiPWype5GZRdHPI/edit#gid=0) is the sample template for this schema to see the kind of data and template in which cQube will accept data.
