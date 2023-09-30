# Error during ingestion



| ID | State / UT Name                      |
| -- | ------------------------------------ |
| 1  | Andaman and Nicobar Islands          |
| 2  | Andhra Pradesh                       |
| 3  | Arunachal Pradesh                    |
| 4  | Assam                                |
| 5  | Bihar                                |
| 6  | Chandigarh                           |
| 7  | Chhattisgarh                         |
| 8  | Dadra & Nagar Haveli and Daman & Diu |
| 9  | Delhi                                |
| 10 | Goa                                  |
| 11 | Gujarat                              |
| 12 | Haryana                              |
| 13 | Himachal Pradesh                     |
| 14 | Jammu and Kashmir                    |
| 15 | Jharkhand                            |
| 16 | Karnataka                            |
| 17 | Kerala                               |
| 18 | Ladakh                               |
| 19 | Lakshadweep                          |
| 20 | Madhya Pradesh                       |
| 21 | Maharashtra                          |
| 22 | Manipur                              |
| 23 | Meghalaya                            |
| 24 | Mizoram                              |
| 25 | Nagaland                             |
| 26 | Odisha                               |
| 27 | Puducherry                           |
| 28 | Punjab                               |
| 29 | Rajasthan                            |
| 30 | Sikkim                               |
| 31 | Tamil Nadu                           |
| 32 | Telangana                            |
| 33 | Tripura                              |
| 34 | Uttar Pradesh                        |
| 35 | Uttarakhand                          |
| 36 | West Bengal                          |
| 37 | CBSE                                 |
| 38 | CISCE                                |
| 39 | NCERT                                |

### Single Master of Districts, Blocks, Clusters and Schools within a state to be referenced:

* State and national programs on cQube will require data for districts, blocks, clusters and schools to enable decentralised observability. Dimension masters for district, block, cluster and school will need to be created having a unique ID and name of the jurisdiction. A single master file for each jurisdiction should be created and that should be referenced for data of both - state as well as national programs. Any discrepancy will lead to unsuccessful data ingestion.
* For example: If a state has 30 districts, a district dimension master will have data in[ this](https://cqube.sunbird.org/data-ingestion-and-processing/cqube-schemas#district-dimension) format. The table will contain IDs from 1 to 30 with names of the district against each ID. Each district will be mapped to the state ID as per the 1st point. Same process will be followed for dimension masters for blocks, clusters and schools.

### Individual values for grade, subject and medium instead of arrays:

* State and national programs in cQube will require data for grade, subject and medium being followed in the state. Generally the states share values of subject in arrays like \['Political Science/Civics', 'Social Science']. This is an incorrect format.
* The subjects should have individual values and different subjects should be in different rows. For example: Political Science / Civics will be Row 1 with relevant data in the event file and Social Science will be Row 2 with relevant data in the event file. Dimension for subject in the specified format linked here will also have 2 rows with unique IDs - Political Science / Civics and Social Science.

### Change in column name in diksha\_nishtha\_percentage-enrollment-certification.zip for NISHTHA Program:

* File from NCERT Team will contain 2 duplicate column names for diksha\_nishtha\_percentage-enrollment-certification.zip for NISHTHA program : State and State.
* Change the first State column (Column B) to State Name\_Correct.

### No quotes - single (') or double (“) should be present in the data being ingested

* In all the files being ingested, single or double quotes should not be present at all

## Error Monitoring

## Accessing error files in AWS

<figure><img src="https://lh6.googleusercontent.com/ImNNOQ3E55gIRphxZer9S8_bGFE7JC3j1LGs1PoSz-ptUuNz8rKJbOGs2cEg6ix_t2EQyjI_p7-Vx_J-O8ekw8xPOLkmFnjfYoKsh1O14jJgUcXQd33pjmmUOKHHNvm6OhRE5km4sZiDaFD5sYlGd5M" alt=""><figcaption></figcaption></figure>

<figure><img src="https://lh5.googleusercontent.com/Zn2im2wsxMDUGt9uqEK1q86dT6zEjAJ88uqSDEGoOZvb3YYwY51LiaMeXRzcctfS_zBPPbcw8VyndDLmj3kPdhMHdXV0aE9CKe7LJwiR0y5fSapf80zedSZTHmN2-m-k4u3nWZHqJHtDQs8XChLEUw8" alt=""><figcaption></figcaption></figure>

<figure><img src="https://lh6.googleusercontent.com/lp0xGtfdgLSECHq_EIpsQ-LjBmJpHdttFCdR3dcZUJzH9CL8-dmAcot_AvplbxZ06k4_UFryWMznrAswIxNXXNTkhNs8QYQJRBazpeyqm1yAiBHOpPQEk4TR9KkemQUwDsKI-ebRi3JfuLZTVv9WqDQ" alt=""><figcaption></figcaption></figure>

<figure><img src="https://lh6.googleusercontent.com/AWD6HWTY-1cgvSinQUZotwzxpZ2RKvqUdrVTNUHwRInByr-5vsybHbYsBAjYBpNNCFpyyvTnhEntB6fbqhwLwp-8yIazgdgin4NE_0A_BUKcNz1D2S70GJxogHIJdzZG2_clw-WejFOKvCowiWbBE4U" alt=""><figcaption></figcaption></figure>

To get the count of processed records and error records GET /ingestion/file-status API can be used.
