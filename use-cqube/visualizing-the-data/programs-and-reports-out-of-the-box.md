---
description: >-
  Details out the indicators in each report and program available in cQube Ed V
  5.0
---

# Programs and reports out-of-the-box

There are a total of 9 programs available in cQube v5.0:

1. [Student Attendance](programs-and-reports-out-of-the-box.md#1.-student-attendance)
2. [NISHTHA](programs-and-reports-out-of-the-box.md#2.-nishtha)
3. [DIKSHA](programs-and-reports-out-of-the-box.md#3.-diksha)
4. [PM POSHAN](programs-and-reports-out-of-the-box.md#4.-pm-poshan)
5. [NAS](programs-and-reports-out-of-the-box.md#5.-nas)
6. [UDISE](programs-and-reports-out-of-the-box.md#6.-udise)
7. [PGI](programs-and-reports-out-of-the-box.md#7.-pgi)

### 1. Student Attendance

This program entails indicators to monitor compliance and performance of student attendance. Following are the reports within this program.

* **Schools Reporting Student Attendance:** This report shows the % of schools that report attendance within the selected time duration for more than 50% enrolled students on average. This report will have the Date Range filter. Other Filters like District, Block, Cluster, School will be picked up from RBAC. Following indicators will be available for specific roles as part of this report:

For a State Officer:

<table data-full-width="true"><thead><tr><th>Indicator</th><th>Chart Type</th><th>Applicable Filters</th></tr></thead><tbody><tr><td>Average % Schools Reporting Student Attendance</td><td>Big Number</td><td>Date Range</td></tr><tr><td>District-wise % Schools Reporting Student Attendance</td><td>Table</td><td>Date Range</td></tr></tbody></table>

For a District Officer:

<table><thead><tr><th>Indicator</th><th width="133.66666666666666">Chart Type</th><th>Applicable Filters</th></tr></thead><tbody><tr><td>Average % Schools Reporting Student Attendance</td><td>Big Number</td><td>District, Date Range</td></tr><tr><td>Block-wise % Schools Reporting Student Attendance</td><td>Table</td><td>District, Date Range</td></tr><tr><td>District-wise Rank in % Schools Reporting Student Attendance</td><td>Table</td><td>Date Range</td></tr></tbody></table>

For a Block Officer:

| Indicator                                                 | Chart Type | Applicable Filters          |
| --------------------------------------------------------- | ---------- | --------------------------- |
| Average % Schools Reporting Student Attendance            | Big Number | District, Block, Date Range |
| Cluster-wise % Schools Reporting Student Attendance       | Table      | District, Block, Date Range |
| Block-wise Rank in % Schools Reporting Student Attendance | Table      | District, Date Range        |

For a Cluster Officer:

| Indicator                                                   | Chart Type | Applicable Filters                   |
| ----------------------------------------------------------- | ---------- | ------------------------------------ |
| Average % Schools Reporting Student Attendance              | Big Number | District, Block, Cluster, Date Range |
| School-wise % Student attendance being reported             | Table      | District, Block, Cluster, Date Range |
| Cluster-wise Rank in % Schools Reporting Student Attendance | Table      | District, Block, Date Range          |

For a School Principal:

| Indicator                                               | Chart Type | Applicable Filters                           |
| ------------------------------------------------------- | ---------- | -------------------------------------------- |
| Average % Student attendance being reported             | Big Number | District, Block, Cluster, School, Date Range |
| Grade-wise % Student attendance being reported          | Table      | District, Block, Cluster, School, Date Range |
| School-wise Rank in % Student attendance being reported | Table      | District, Block, Cluster, Date Range         |

* **Average Students Present:** This report shows the % of students present (out of the ones for whom attendance is being reported) within the selected time duration on an average. This report will have the Date Range filter. Other Filters like District, Block, Cluster, School will be picked up from RBAC. Following indicators will be available for specific roles as part of this report:

For a State Officer:

<table><thead><tr><th width="252.66666666666666">Indicator</th><th>Chart Type</th><th>Applicable Filters</th></tr></thead><tbody><tr><td>Average % Students Present</td><td>Big Number</td><td>Date Range</td></tr><tr><td>District-wise % Students Present</td><td>Table</td><td>Date Range</td></tr><tr><td>Gender-wise % Students Present</td><td>Bar Chart</td><td>Date Range</td></tr><tr><td>Grade-wise % Students Present</td><td>Bar Chart</td><td>Date Range</td></tr></tbody></table>

For a District Officer:

| Indicator                                | Chart Type | Applicable Filters   |
| ---------------------------------------- | ---------- | -------------------- |
| Average % Students Present               | Big Number | District, Date Range |
| Block-wise % Students Present            | Table      | District, Date Range |
| District-wise Rank in % Students Present | Table      | Date Range           |
| Gender-wise % Students Present           | Bar Chart  | District, Date Range |
| Grade-wise % Students Present            | Bar Chart  | District, Date Range |

For a Block Officer:

| Indicator                             | Chart Type | Applicable Filters          |
| ------------------------------------- | ---------- | --------------------------- |
| Average % Students Present            | Big Number | District, Block, Date Range |
| Cluster-wise % Students Present       | Table      | District, Block, Date Range |
| Block-wise Rank in % Students Present | Table      | District, Date Range        |
| Gender-wise % Students Present        | Bar Chart  | District, Block, Date Range |
| Grade-wise % Students Present         | Bar Chart  | District, Block, Date Range |

For a Cluster Officer:

| Indicator                               | Chart Type | Applicable Filters                   |
| --------------------------------------- | ---------- | ------------------------------------ |
| Average % Students Present              | Big Number | District, Block, Cluster, Date Range |
| School-wise % Students Present          | Table      | District, Block, Cluster, Date Range |
| Cluster-wise Rank in % Students Present | Table      | District, Block, Date Range          |
| Gender-wise % Students Present          | Bar Chart  | District, Block, Cluster, Date Range |
| Grade-wise % Students Present           | Bar Chart  | District, Block, Cluster, Date Range |

For a School Principal:

| Indicator                      | Chart Type | Applicable Filters                           |
| ------------------------------ | ---------- | -------------------------------------------- |
| Average % Students Present     | Big Number | District, Block, Cluster, School, Date Range |
| Grade-wise % Students Present  | Table      | District, Block, Cluster, School, Date Range |
| School-wise % Students Present | Table      | District, Block, Cluster, Date Range         |
| Gender-wise % Students Present | Bar Chart  | District, Block, Cluster, School, Date Range |

For a Class Teacher:

| Indicator                             | Chart Type | Applicable Filters                                  |
| ------------------------------------- | ---------- | --------------------------------------------------- |
| % Students Present                    | Big Number | District, Block, Cluster, School, Grade, Date Range |
| Grade-wise Rank in % Students Present | Table      | District, Block, Cluster, School, Date Range        |
| Gender-wise % Students Present        | Bar Chart  | District, Block, Cluster, School, Grade, Date Range |

* **Average Students Present:** This report shows the % of students present (out of the ones for whom attendance is being reported) within the selected time duration on an average. This report will have the Date Range filter. Other Filters like District, Block, Cluster, School will be picked up from RBAC. Following indicators will be available for specific roles as part of this report:

For a State Officer:

<table><thead><tr><th width="252.66666666666666">Indicator</th><th>Chart Type</th><th>Applicable Filters</th></tr></thead><tbody><tr><td>Average % Students Present</td><td>Big Number</td><td>Date Range</td></tr><tr><td>District-wise % Students Present</td><td>Table</td><td>Date Range</td></tr><tr><td>Gender-wise % Students Present</td><td>Bar Chart</td><td>Date Range</td></tr><tr><td>Grade-wise % Students Present</td><td>Bar Chart</td><td>Date Range</td></tr></tbody></table>

For a District Officer:

| Indicator                                | Chart Type | Applicable Filters   |
| ---------------------------------------- | ---------- | -------------------- |
| Average % Students Present               | Big Number | District, Date Range |
| Block-wise % Students Present            | Table      | District, Date Range |
| District-wise Rank in % Students Present | Table      | Date Range           |
| Gender-wise % Students Present           | Bar Chart  | District, Date Range |
| Grade-wise % Students Present            | Bar Chart  | District, Date Range |

For a Block Officer:

| Indicator                             | Chart Type | Applicable Filters          |
| ------------------------------------- | ---------- | --------------------------- |
| Average % Students Present            | Big Number | District, Block, Date Range |
| Cluster-wise % Students Present       | Table      | District, Block, Date Range |
| Block-wise Rank in % Students Present | Table      | District, Date Range        |
| Gender-wise % Students Present        | Bar Chart  | District, Block, Date Range |
| Grade-wise % Students Present         | Bar Chart  | District, Block, Date Range |

For a Cluster Officer:

| Indicator                               | Chart Type | Applicable Filters                   |
| --------------------------------------- | ---------- | ------------------------------------ |
| Average % Students Present              | Big Number | District, Block, Cluster, Date Range |
| School-wise % Students Present          | Table      | District, Block, Cluster, Date Range |
| Cluster-wise Rank in % Students Present | Table      | District, Block, Date Range          |
| Gender-wise % Students Present          | Bar Chart  | District, Block, Cluster, Date Range |
| Grade-wise % Students Present           | Bar Chart  | District, Block, Cluster, Date Range |

For a School Principal:

| Indicator                      | Chart Type | Applicable Filters                           |
| ------------------------------ | ---------- | -------------------------------------------- |
| Average % Students Present     | Big Number | District, Block, Cluster, School, Date Range |
| Grade-wise % Students Present  | Table      | District, Block, Cluster, School, Date Range |
| School-wise % Students Present | Table      | District, Block, Cluster, Date Range         |
| Gender-wise % Students Present | Bar Chart  | District, Block, Cluster, School, Date Range |

For a Class Teacher:

| Indicator                             | Chart Type | Applicable Filters                                  |
| ------------------------------------- | ---------- | --------------------------------------------------- |
| % Students Present                    | Big Number | District, Block, Cluster, School, Grade, Date Range |
| Grade-wise Rank in % Students Present | Table      | District, Block, Cluster, School, Date Range        |
| Gender-wise % Students Present        | Bar Chart  | District, Block, Cluster, School, Grade, Date Range |

### 2. NISHTHA

NISHTHA is a capacity building program for "Improving Quality of School Education through Integrated Teacher Training". It aims to build competencies among all the teachers and school principals at the elementary stage. NISHTHA is the world's largest teachers' training program. Following reports are available in this program:

1. Implementation Status
2. Courses and Medium status
3. % against Potential Base
4. District wise Status
5. Course wise Status

### **3. DIKSHA:**

The Digital Infrastructure for Knowledge Sharing is an initiative of the National Council of Educational Research and Training (Ministry of Education, Govt. of India). This platform enables implementation of two key programs- NISHTHA and Energized Textbooks. Following reports are available in this program:

1. ETB Coverage Status
2. Content Coverage on QR
3. Learning Sessions on Potential Users

### **4. PM POSHAN:**

Pradhan Mantri Poshan Shakti Nirman (PM POSHAN) earlier known as the National Programme of Mid-Day Meal in Schools is one of the foremost rights based Centrally Sponsored Schemes under the National Food Security Act, 2013 (NFSA). The primary objective of the scheme is to improve the nutritional status of children studying in classes I-VIII in eligible schools. Following report is available in this program:

1. Progress Status

### **5. NAS:**

The National Achievement Survey (NAS) is a nationally representative large-scale survey of students' learning undertaken by the Ministry of Education, Government of India. Following reports are available in this program:

1. District Wise Performance
2. Grade & Subject performance

### **6. UDISE:**

The Unified District Information System for Education (UDISE) is an educational management information system collected by school administrators on a yearly basis. Following reports are available in this program:

1. District Wise Performance
2. Correlation

### **7. PGI:**

The Performance Grading Index (PGI) is a tool to provide insights on the status of school education in States and Union territories including key levers that drive their performance and critical areas for improvement. Following report is available in this program:

1. District Wise Performance
