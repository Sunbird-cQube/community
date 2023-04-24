---
description: Describes the common errors to be considered during data ingestion into cQube
---

# Common errors during ingestion

The state tech team, while ingesting data for both state and national programs, should make sure that the following errors are rectified and taken care of in the data being ingested into cQube.

1. [Global Master of States and UTs](common-errors-during-ingestion.md#global-master-of-states-and-uts)
2. [Single Master of Districts, Blocks, Clusters and Schools within a state to be referenced](common-errors-during-ingestion.md#single-master-of-districts-blocks-clusters-and-schools-within-a-state-to-be-referenced)
3. [Individual values for grade, subject and medium instead of arrays](common-errors-during-ingestion.md#individual-values-for-grade-subject-and-medium-instead-of-arrays)
4. [Change in column name in _diksha\_nishtha\_percentage-enrollment-certification.zip_ for NISHTHA program](common-errors-during-ingestion.md#change-in-column-name-in-diksha\_nishtha\_percentage-enrollment-certification.zip-for-nishtha-program)
5. [No quotes - single (') or double (") should be present in the data being ingested](common-errors-during-ingestion.md#no-quotes-single-or-double-should-be-present-in-the-data-being-ingested)

### **Global Master of States and UTs:**

* A state master is specified in cQube. These state codes should be referenced while ingesting data within cQube for state and district dimensions and for respective event tables.
* Following is the master for States and UTs:

| State / UT Code | State / UT Name                      |
| --------------- | ------------------------------------ |
| 1               | Andaman and Nicobar Islands          |
| 2               | Andhra Pradesh                       |
| 3               | Arunachal Pradesh                    |
| 4               | Assam                                |
| 5               | Bihar                                |
| 6               | Chandigarh                           |
| 7               | Chhattisgarh                         |
| 8               | Dadra & Nagar Haveli and Daman & Diu |
| 9               | Delhi                                |
| 10              | Goa                                  |
| 11              | Gujarat                              |
| 12              | Haryana                              |
| 13              | Himachal Pradesh                     |
| 14              | Jammu and Kashmir                    |
| 15              | Jharkhand                            |
| 16              | Karnataka                            |
| 17              | Kerala                               |
| 18              | Ladakh                               |
| 19              | Lakshadweep                          |
| 20              | Madhya Pradesh                       |
| 21              | Maharashtra                          |
| 22              | Manipur                              |
| 23              | Meghalaya                            |
| 24              | Mizoram                              |
| 25              | Nagaland                             |
| 26              | Odisha                               |
| 27              | Puducherry                           |
| 28              | Punjab                               |
| 29              | Rajasthan                            |
| 30              | Sikkim                               |
| 31              | Tamil Nadu                           |
| 32              | Telangana                            |
| 33              | Tripura                              |
| 34              | Uttar Pradesh                        |
| 35              | Uttarakhand                          |
| 36              | West Bengal                          |
| 37              | CBSE                                 |
| 38              | CISCE                                |
| 39              | NCERT                                |

### **Single Master of Districts, Blocks, Clusters and Schools within a state to be referenced:**

* State and national programs on cQube will require data for districts, blocks, clusters and schools to enable decentralised observability. Dimension masters for district, block, cluster and school will need to be created having a unique ID and name of the jurisdiction. A single master file for each jurisdiction should be created and that should be referenced for data of both - state as well as national programs. Any discrepancy will lead to unsuccessful data ingestion.
* For example: If a state has 30 districts, a district dimension master will have data in [this](cqube-schemas.md#district-dimension) format. The table will contain IDs from 1 to 30 with names of the district against each ID. Each district will be mapped to the state ID as per the 1st point. Same process will be followed for dimension masters for blocks, clusters and schools.

### **Individual values for grade, subject and medium instead of arrays:**

* State and national programs in cQube will require data for grade, subject and medium being followed in the state. Generally the states share values of subject in arrays like \['Political Science/Civics', 'Social Science']. This is an incorrect format.
* The subjects should have individual values and different subjects should be in different rows. For example: Political Science / Civics will be Row 1 with relevant data in the event file and Social Science will be Row 2 with relevant data in the event file. Dimension for subject in the specified format linked here will also have 2 rows with unique IDs - Political Science / Civics and Social Science.

### **Change in column name in **_**diksha\_nishtha\_percentage-enrollment-certification.zip**_** for NISHTHA Program:**

* File from NCERT Team will contain 2 duplicate column names for _diksha\_nishtha\_percentage-enrollment-certification.zip_ for NISHTHA program : State and State.
* Change the first State column (Column B) to State Name\_Correct.

### **No quotes - single (') or double (“) should be present in the data being ingested**

* In all the files being ingested, single or double quotes should not be present at all.
