# Common errors in data files during ingestion

### Single Master of Districts, Blocks, Clusters and Schools within a state to be referenced:

* State and national programs on cQube will require data for districts, blocks, clusters and schools to enable decentralised observability. Dimension masters for district, block, cluster and school will need to be created having a unique ID and name of the jurisdiction. A single master file for each jurisdiction should be created and that should be referenced for data of both - state as well as national programs. Any discrepancy will lead to unsuccessful data ingestion.
* For example: If a state has 30 districts, a district dimension master will have data in[ this](https://cqube.sunbird.org/data-ingestion-and-processing/cqube-schemas#district-dimension) format. The table will contain IDs from 1 to 30 with names of the district against each ID. Each district will be mapped to the state ID as per the 1st point. Same process will be followed for dimension masters for blocks, clusters and schools.

### Individual values for grade, subject and medium instead of arrays:

* State and national programs in cQube will require data for grade, subject and medium being followed in the state. Generally the states share values of subject in arrays like \['Political Science/Civics', 'Social Science']. This is an incorrect format.
* The subjects should have individual values and different subjects should be in different rows. For example: Political Science / Civics will be Row 1 with relevant data in the event file and Social Science will be Row 2 with relevant data in the event file. Dimension for subject in the specified format linked here will also have 2 rows with unique IDs - Political Science / Civics and Social Science.

### No quotes - single (') or double (“) should be present in the data being ingested

* In all the files being ingested, single or double quotes should not be present at all
