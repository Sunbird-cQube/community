---
description: Details out the indicators in each report and program available in cQube v5.0
---

# Programs, Reports & Indicators

There are a total of 9 programs available in cQube v5.0:

1. [Student Attendance](programs-reports-and-indicators.md#1.-student-attendance)
2. [Teacher Attendance](programs-reports-and-indicators.md#2.-teacher-attendance)
3. [Review Meetings](programs-reports-and-indicators.md#3.-review-meetings)
4. DIKSHA
5. NISHTHA
6. PM POSHAN
7. NAS
8. PGI
9. UDISE

### 1. Student Attendance

This program entails indicators to monitor compliance and performance of student attendance. Following are the reports within this program.

* **Student Attendance Compliance:** This report shows the compliance of student attendance being marked in the schools. A school is counted as attendance-compliant when attendance of more than 50% of the students in the school is marked on a particular date. This report will have the Date Range filter. Other Filters like District, Block, Cluster, School will be picked up from RBAC. Following indicators will be available for specific roles as part of this report:

For a State Officer:

| Indicator                             | Chart Type | Applicable Filters |
| ------------------------------------- | ---------- | ------------------ |
| Average Attendance Compliance %       | Big Number | Date Range         |
| District-wise Attendance Compliance % | Table      | Date Range         |

For a District Officer:

| Indicator                                     | Chart Type | Applicable Filters   |
| --------------------------------------------- | ---------- | -------------------- |
| Average Attendance Compliance %               | Big Number | District, Date Range |
| Block-wise Attendance Compliance %            | Table      | District, Date Range |
| District-wise Rank in Attendance Compliance % | Table      | Date Range           |

For a Block Officer:

| Indicator                                  | Chart Type | Applicable Filters          |
| ------------------------------------------ | ---------- | --------------------------- |
| Average Attendance Compliance %            | Big Number | District, Block, Date Range |
| Cluster-wise Attendance Compliance %       | Table      | District, Block, Date Range |
| Block-wise Rank in Attendance Compliance % | Table      | District, Date Range        |

For a Cluster Officer:

| Indicator                                    | Chart Type | Applicable Filters                   |
| -------------------------------------------- | ---------- | ------------------------------------ |
| Average Attendance Compliance %              | Big Number | District, Block, Cluster, Date Range |
| School-wise Attendance Compliance %          | Table      | District, Block, Cluster, Date Range |
| Cluster-wise Rank in Attendance Compliance % | Table      | District, Block, Date Range          |

For a School Principal:

| Indicator                                    | Chart Type | Applicable Filters                           |
| -------------------------------------------- | ---------- | -------------------------------------------- |
| Average Attendance Compliance %              | Big Number | District, Block, Cluster, School, Date Range |
| Grade-wise Attendance Compliance % (1 to 12) | Table      | District, Block, Cluster, School, Date Range |
| School-wise Rank in Attendance Compliance %  | Table      | District, Block, Cluster, Date Range         |

* **Student Attendance Summary:** This report shows the summary of students being present in the schools (out of the ones being marked). This report will have the Date Range filter. Other Filters like District, Block, Cluster, School will be picked up from RBAC. Following indicators will be available for specific roles as part of this report:

For a State Officer:

| Indicator                                                                     | Chart Type | Applicable Filters |
| ----------------------------------------------------------------------------- | ---------- | ------------------ |
| Average Attendance %                                                          | Big Number | Date Range         |
| District-wise Attendance %                                                    | Table      | Date Range         |
| Gender-wise Attendance % (Male, Female, Other)                                | Bar Chart  | Date Range         |
| Grade-wise Attendance % (Primary, Upper Primary, Secondary, Senior Secondary) | Bar Chart  | Date Range         |

For a District Officer:

| Indicator                                                                     | Chart Type | Applicable Filters   |
| ----------------------------------------------------------------------------- | ---------- | -------------------- |
| Average Attendance %                                                          | Big Number | District, Date Range |
| Block-wise Attendance %                                                       | Table      | District, Date Range |
| District-wise Rank in Attendance %                                            | Table      | Date Range           |
| Gender-wise Attendance % (Male, Female, Other)                                | Bar Chart  | District, Date Range |
| Grade-wise Attendance % (Primary, Upper Primary, Secondary, Senior Secondary) | Bar Chart  | District, Date Range |

For a Block Officer:

| Indicator                                                                     | Chart Type | Applicable Filters          |
| ----------------------------------------------------------------------------- | ---------- | --------------------------- |
| Average Attendance %                                                          | Big Number | District, Block, Date Range |
| Cluster-wise Attendance %                                                     | Table      | District, Block, Date Range |
| Block-wise Rank in Attendance %                                               | Table      | District, Date Range        |
| Gender-wise Attendance % (Male, Female, Other)                                | Bar Chart  | District, Block, Date Range |
| Grade-wise Attendance % (Primary, Upper Primary, Secondary, Senior Secondary) | Bar Chart  | District, Block, Date Range |

For a Cluster Officer:

| Indicator                                                                     | Chart Type | Applicable Filters                   |
| ----------------------------------------------------------------------------- | ---------- | ------------------------------------ |
| Average Attendance %                                                          | Big Number | District, Block, Cluster, Date Range |
| School-wise Attendance %                                                      | Table      | District, Block, Cluster, Date Range |
| Cluster-wise Rank in Attendance %                                             | Table      | District, Block, Date Range          |
| Gender-wise Attendance % (Male, Female, Other)                                | Bar Chart  | District, Block, Cluster, Date Range |
| Grade-wise Attendance % (Primary, Upper Primary, Secondary, Senior Secondary) | Bar Chart  | District, Block, Cluster, Date Range |

For a School Principal:

| Indicator                                      | Chart Type | Applicable Filters                           |
| ---------------------------------------------- | ---------- | -------------------------------------------- |
| Average Attendance %                           | Big Number | District, Block, Cluster, School, Date Range |
| Grade-wise Attendance % (1 to 12)              | Table      | District, Block, Cluster, School, Date Range |
| School-wise Rank in Attendance %               | Table      | District, Block, Cluster, Date Range         |
| Gender-wise Attendance % (Male, Female, Other) | Bar Chart  | District, Block, Cluster, School, Date Range |

For a Class Teacher:

| Indicator                                      | Chart Type | Applicable Filters                                  |
| ---------------------------------------------- | ---------- | --------------------------------------------------- |
| Average Attendance %                           | Big Number | District, Block, Cluster, School, Grade, Date Range |
| Grade-wise Rank in Attendance %                | Table      | District, Block, Cluster, School, Date Range        |
| Gender-wise Attendance % (Male, Female, Other) | Bar Chart  | District, Block, Cluster, School, Grade, Date Range |

### 2. Teacher Attendance

This program entails indicators to monitor compliance and performance of teacher attendance. Following are the reports within this program:

* **Teacher Attendance Compliance:** This report shows the compliance of attendance being marked by teachers. This report will have the Date Range filter. Other Filters like District, Block, Cluster, School will be picked up from RBAC. Following indicators will be available for specific roles as part of this report:

For a State Officer:

| Indicator                             | Chart Type | Applicable Filters |
| ------------------------------------- | ---------- | ------------------ |
| Average Attendance Compliance %       | Big Number | Date Range         |
| District-wise Attendance Compliance % | Table      | Date Range         |

For a District Officer:

| Indicator                                     | Chart Type | Applicable Filters   |
| --------------------------------------------- | ---------- | -------------------- |
| Average Attendance Compliance %               | Big Number | District, Date Range |
| Block-wise Attendance Compliance %            | Table      | District, Date Range |
| District-wise Rank in Attendance Compliance % | Table      | Date Range           |

For a Block Officer:

| Indicator                                  | Chart Type | Applicable Filters          |
| ------------------------------------------ | ---------- | --------------------------- |
| Average Attendance Compliance %            | Big Number | District, Block, Date Range |
| Cluster-wise Attendance Compliance %       | Table      | District, Block, Date Range |
| Block-wise Rank in Attendance Compliance % | Table      | District, Date Range        |

For a Cluster Officer:

| Indicator                                    | Chart Type | Applicable Filters                   |
| -------------------------------------------- | ---------- | ------------------------------------ |
| Average Attendance Compliance %              | Big Number | District, Block, Cluster, Date Range |
| School-wise Attendance Compliance %          | Table      | District, Block, Cluster, Date Range |
| Cluster-wise Rank in Attendance Compliance % | Table      | District, Block, Date Range          |

For a School Principal:

| Indicator                                   | Chart Type | Applicable Filters                           |
| ------------------------------------------- | ---------- | -------------------------------------------- |
| Average Attendance Compliance %             | Big Number | District, Block, Cluster, School, Date Range |
| School-wise Rank in Attendance Compliance % | Table      | District, Block, Cluster, Date Range         |

* **Teacher Attendance Summary:** This report shows the summary of teachers being present in the school (out of the ones marking their attendance). This report will have the Date Range filter. Other Filters like District, Block, Cluster, School will be picked up from RBAC. Following indicators will be available for specific roles as part of this report:

For a State Officer:

| Indicator                  | Chart Type | Applicable Filters |
| -------------------------- | ---------- | ------------------ |
| Average Attendance %       | Big Number | Date Range         |
| District-wise Attendance % | Table      | Date Range         |

For a District Officer:

| Indicator                          | Chart Type | Applicable Filters   |
| ---------------------------------- | ---------- | -------------------- |
| Average Attendance %               | Big Number | District, Date Range |
| Block-wise Attendance %            | Table      | District, Date Range |
| District-wise Rank in Attendance % | Table      | Date Range           |

For a Block Officer:

| Indicator                       | Chart Type | Applicable Filters          |
| ------------------------------- | ---------- | --------------------------- |
| Average Attendance %            | Big Number | District, Block, Date Range |
| Cluster-wise Attendance %       | Table      | District, Block, Date Range |
| Block-wise Rank in Attendance % | Table      | District, Date Range        |

For a Cluster Officer:

| Indicator                         | Chart Type | Applicable Filters                   |
| --------------------------------- | ---------- | ------------------------------------ |
| Average Attendance %              | Big Number | District, Block, Cluster, Date Range |
| School-wise Attendance %          | Table      | District, Block, Cluster, Date Range |
| Cluster-wise Rank in Attendance % | Table      | District, Block, Date Range          |

For a School Principal:

| Indicator                        | Chart Type | Applicable Filters                           |
| -------------------------------- | ---------- | -------------------------------------------- |
| Average Attendance %             | Big Number | District, Block, Cluster, School, Date Range |
| School-wise Rank in Attendance % | Table      | District, Block, Cluster, Date Range         |

### 3. Review Meetings

This program entails indicators to monitor compliance of monthly review meetings being conducted at all levels. This program will have the Academic Year & Month filters. Other Filters like District, Block will be picked up from RBAC. Following indicators will be available for specific roles as part of this program:

\
For a State Officer:

| Indicator                                                   | Chart Type | Applicable Filters   |
| ----------------------------------------------------------- | ---------- | -------------------- |
| % districts with review meeting conducted last month        | Big Number | Academic Year, Month |
| District-wise status of review meeting conducted last month | Table      | Academic Year, Month |
| District-wise % blocks conducted meeting last month         | Table      | Academic Year, Month |

For a District Officer:

| Indicator                                                | Chart Type | Applicable Filters             |
| -------------------------------------------------------- | ---------- | ------------------------------ |
| % blocks with review meeting conducted last month        | Big Number | District, Academic Year, Month |
| Block-wise status of review meeting conducted last month | Table      | District, Academic Year, Month |
| Block-wise % clusters conducted meeting last month       |  Table     | District, Academic Year, Month |

For a Block Officer:

| Indicator                                                  | Chart Type |                                       |
| ---------------------------------------------------------- | ---------- | ------------------------------------- |
| % Clusters with review meeting conducted last month        | Big Number | District, Block, Academic Year, Month |
| Cluster-wise status of review meeting conducted last month | Table      | District, Block, Academic Year, Month |

### 4. NISHTHA

NISHTHA is a capacity building programme for "Improving Quality of School Education through Integrated Teacher Training". It aims to build competencies among all the teachers and school principals at the elementary stage. NISHTHA is the world's largest teachers' training program. Following reports are available in this program:

1. Implementation Status
2. Courses and Medium status
3. % against Potential Base
4. District wise Status
5. Course wise Status

### **5. DIKSHA:**

The Digital Infrastructure for Knowledge Sharing is an initiative of the National Council of Educational Research and Training (Ministry of Education, Govt. of India). This platform enables implementation of two key programs- Nishtha and Energized Textbooks. Following reports are available in this program:

1. ETB Coverage Status
2. Content Coverage on QR
3. Learning Sessions
4. Learning Sessions on Potential Users

### **6. PM POSHAN:**

Pradhan Mantri Poshan Shakti Nirman (PM POSHAN) earlier known as the National Programme of Mid-Day Meal in Schools is one of the foremost rights based Centrally Sponsored Schemes under the National Food Security Act, 2013 (NFSA). The primary objective of the scheme is to improve the nutritional status of children studying in classes I-VIII in eligible schools. Following report is available in this program:

1. Progress Status

### **7. NAS:**

The National Achievement Survey (NAS) is a nationally representative large-scale survey of students' learning undertaken by the Ministry of Education, Government of India. Following reports are available in this program:

1. District Wise Performance
2. Grade & Subject performance

### **8. UDISE:**

The Unified District Information System for Education (UDISE) is an educational management information system collected by school administrators on a yearly basis. Following reports are available in this program:

1. District Wise Performance
2. Correlation

### **9. PGI:**

The Performance Grading Index (PGI) is a tool to provide insights on the status of school education in States and Union territories including key levers that drive their performance and critical areas for improvement. Following report is available in this program:

1. District Wise Performance

\
