# Data Storage Locations



* S3 emission data Location: The data emitted from the state education system has to be

  stored until the NIFI reads the data. S3 emission storage buckets are the storage

  locations where the emitted data files are stored.

* S3 Input Data: This is a location where the raw data resides for all future references.
* PostgreSQL: All the transformed and aggregated data will be stored in PostgreSQL

  tables.

* S3 Output Data: A location where the processed data resides in JSON format.

