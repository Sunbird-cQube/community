# Data Validation after Ingestion

NIFI fetches the data from the S3 emission bucket/data folder and sends it to the S3 input bucket/data folder. Once the data is sent to input bucket/data folder the following validations are performed:

* Column level validations: Column datatype mismatch, Number of columns, Data exceeding the column size.
* Improper Data handling: Missing/ null data values for mandatory fields, Empty data files, Special characters, Blank lines in data files.
* Duplicate records validation: NIFI validates the duplicate records by grouping the same kind of records together.

Validation for duplicate records: Records which have duplicate values for all fields \(mirror  record\) then NIFI will consider the first record and the rest of the records will be eliminated. 

**Records with duplicate ID:** For the rest of the duplicate records where the records are having the same ID \(the primary/composite key like student ID/ assessment ID/ infra ID/ CRC visit ID\) and different values for rest of the columns will not be inserted into the database tables as ID is the primary key.

**Example:** For the Duplicate records with different lat long details for school\_master data file,  NIFI eliminates the records which have the same school\_id with different lat long details or different names or different values.

**Records with same values:** For semester report, The records which are having the same values for fields Student ID, School ID, semester, studying class and different values for the subjects then NIFI will eliminate those records. 

**Overlapping data validation:** Overlapping data validation takes place based on the data source.

* The NIFI process for student attendance reports will check the last updated day’s record from the transaction table and will process the records from the day after the last updated date. The records from all of the previous days will not be considered for NIFI processing. 
* For the other data sources, duplicate records where the records are having the same ID \(student ID/ assessment ID/ infra ID/ CRC visit ID\) and different values will not be inserted into the database tables as ID is the primary key.

**Other data issues:** Data handling in cases like job failures, missing data for certain days and late receipt of the data \(receiving data after a few days\), updating the wrong data, upon request \(when issue identified at the report\)  


