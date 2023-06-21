---
description: >-
  This page focusses on ingestion of programs like UDISE, PGI, NISHTHA, DIKSHA,
  NAS, PM-POSHAN.
---

# Step-wise Ingestion Process \[National Programs]

**Note: **_**There could be some common errors in the files which could lead to unsuccessful data ingestion into cQube. Look at these errors here and resolve them before ingesting data into cQube.**_

_**The already existing files will need to be ingested into cQube via the following process:**_

_**This API accepts the data in a zip file format and adds it to the emission folder in the respective cloud storage / SDC.**_

\
**Step 1:** Open the specified request and add the details.

API Endpoint: \<domain\_name>/ingestion/national\_programs

HTTP Method: POST

<figure><img src="https://lh3.googleusercontent.com/N_8O9_fJZc9wfpeBot25EAJWRj31GnoJSY-I1bmMLQXysBwXYLwiLt11FiQhMq2h1lrwtYR3JBTWeOgTPUP6ouT9b3FCA1Th0lhjSdBQBb3dfBQc8SThUc0WN8BVfyeIJLO8bjUQTt8GhzRxxWKN9rQ" alt=""><figcaption></figcaption></figure>

**Step 2:** Build the request body with reference to YAML file. The request body for the above API is attached here for yaml:[https://github.com/Sunbird-cQube/spec-ms/blob/dev/spec.yaml](https://github.com/Sunbird-cQube/spec-ms/blob/dev/spec.yaml). [ ](https://github.com/Sunbird-cQube/spec-ms/blob/march-release/spec.yaml)

Provide the valid input details for the parameters as shown below.

<figure><img src="https://lh4.googleusercontent.com/5BcevacEEZ8tbvKdy6w2UCl5ZkbM33XWMmMtTOzIVYANBYe-1l5GWppavwL7wWiTaZVes0-YObD1SSoiKn-d5IUMlN2gLX_grm_8pFbYp2NlAP58e4oq7wXdXsvyO_QJEU02GS7oAySRaQ7dcsRjDU8" alt=""><figcaption></figcaption></figure>

**Step 3:** Click on the send button for the request and if the request is successful, the user should see a response message as “File uploaded successfully”. The files will be uploaded to the emission folder created in the respective cloud storage / SDC.

The zip file will be extracted and will be read by the adapters and then moved into the input folders.

![](https://lh4.googleusercontent.com/7MZbJoOVWTyPgK5vOvznXCbqxB7V9Ytv6hBufHpLEg0wyIrdG75\_GgRFdZ5I9LUcQ7WlhYOwxOrCJLFO16dUq2PJ-aq64lFApfRZiuQV8WnVZGZh8RNr7mTX3HqjyJqz7pW2bz0Yo6Kf5AZr6YzzGwY)

###

### Common Errors during Data Ingestion

The state tech team, while ingesting data for both state and national programs, should make sure that the following errors are rectified and taken care of in the data being ingested into cQube.

* **Global Master of States and UTs:**
  * A state master is specified in cQube. These state codes should be referenced while ingesting data within cQube for state and district dimensions and for respective event tables.
  * Following is the master for States and UTs:

\


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

\


*   Single Master of Districts, Blocks, Clusters and Schools within a state to be referenced:

    * State and national programs on cQube will require data for districts, blocks, clusters and schools to enable decentralised observability. Dimension masters for district, block, cluster and school will need to be created having a unique ID and name of the jurisdiction. A single master file for each jurisdiction should be created and that should be referenced for data of both - state as well as national programs. Any discrepancy will lead to unsuccessful data ingestion.
    * **For example**: If a state has 30 districts, a district dimension master will have data in[ this](https://cqube.sunbird.org/data-ingestion-and-processing/cqube-schemas#district-dimension) format. The table will contain IDs from 1 to 30 with names of the district against each ID. Each district will be mapped to the state ID as per the 1st point. Same process will be followed for dimension masters for blocks, clusters and schools.


*   Individual values for grade, subject and medium instead of arrays:

    * State and national programs in cQube will require data for grade, subject and medium being followed in the state. Generally the states share values of subject in arrays like \['Political Science/Civics', 'Social Science']. This is an incorrect format.
    * The subjects should have individual values and different subjects should be in different rows. For example: Political Science / Civics will be Row 1 with relevant data in the event file and Social Science will be Row 2 with relevant data in the event file. Dimension for subject in the specified format linked here will also have 2 rows with unique IDs - Political Science / Civics and Social Science.


*   Change in column name in diksha\_nishtha\_percentage-enrollment-certification.zip for NISHTHA Program:

    * File from NCERT Team will contain 2 duplicate column names for diksha\_nishtha\_percentage-enrollment-certification.zip for NISHTHA program : State and State.
    * Change the first State column (Column B) to State Name\_Correct.


* No quotes - single (') or double (“) should be present in the data being ingested
  * In all the files being ingested, single or double quotes should not be present at all.&#x20;

## Nifi

Here we have different processor groups to process the data(Nifi canvas).

* [To run adapters](./#to-run-adapters)
* [To run all programs](./#to-run-all-programs)
* [To run program wise](./#to-run-program-wise)

<figure><img src="https://lh5.googleusercontent.com/tekP3o7l9nljvLcQvU0ZB5E_eLZVWHzuRxuRFfBBhIpC9wj2cEUJxmRQlyAdyrtIj0AagES_MgNf9m9rgueiXYGBhsA8v0cN-whGugjGqdAKrPtfMMS-qzL-YLO6PrVAOaa8ci3c1LdTiv8Zzl1vu84" alt=""><figcaption></figcaption></figure>

### &#x20;**To run adapters:**

This processor group is used to run the adapters shell script code.

\


<figure><img src="https://lh6.googleusercontent.com/cuo_0hnFF79KGACxy4iLPGO1fzueAE843hZwf-J08XvGZmK7AXXtvr3VqtvHNGyZsXDunwY77mt1mm27CYMgXnMqEluPtrkxQ-SPhToA2PxpSytBIe5AsnCzZAI3ZIzDsXe0k5ZNTuXSTu-z1XrVdNk" alt=""><figcaption></figcaption></figure>

<figure><img src="https://lh6.googleusercontent.com/6e89pGDUKVPY42iAq29Qng4xaFs_2XzM1_pCzRDFKi_bojUzpQ_p_YQkz2iH1gUH6_IsmNLT_nvRJIB86Qnq6ZbB3j46tU4-RR074iiHxHuPeBWP9GykiDiDPQ6it5yZlKuz7ysssIhjxI8XtT-O8Tw" alt=""><figcaption></figcaption></figure>

\


### To run all programs:&#x20;

This processor group is used to move files from process\_input folder to processing\_ms folder according to folder structures. .i.e., (dimensions/,programs/). Then it will run yarn cli ingest(where it will ingest all schemas and grammars to the database) and yarn cli ingest-data (where it will ingest all data files to the database) commands.&#x20;

<figure><img src="https://lh4.googleusercontent.com/beTqN9S42NNiw4f4PSMn1sXH1xtL00JSV2o7wK0hdiW4EdoQX2FgH1PYHR4ogdthEpyvhKe6Hxz_HfTYseMsqThnmk9o5rz2tJyJ3mUcQ7GI0AD5zstw82Cm8EWAJiMidrD8vDKTfl4vFx1amhqzb20" alt=""><figcaption></figcaption></figure>

\


### To run program wise

This processor group is used to move particular program files from process\_input folder to processing\_ms folder. Then it will run yarn cli ingest and yarn cli ingest-data --filter=’program\_name’.(where it will ingest particular program data files).

\
\
In order to automate these processor groups we have written REST-APIs, use: [Nifi-Rest-api’s code](https://github.com/Sunbird-cQube/generator-ms/blob/dev/static\_processor\_group/add\_nifi\_template.py)

<figure><img src="https://lh6.googleusercontent.com/z8g-NAaReyCsM21E7iIcIjlpqVI5EMPrlodrZaYTEZV1xjFX1VMCQMckiB6SiU9wFdb6CqtD5DxqzOnPpZJ-FuPZFcHgJ67RCmaqy6aIZinlDJKWs_XoUVsiAOnOokbugai4SkyQl2DvzXRKAw7CzvQ" alt=""><figcaption></figcaption></figure>



\
