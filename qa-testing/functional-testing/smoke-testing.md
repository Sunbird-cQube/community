# Smoke Testing

When the build is ready for QA then, we will take up the release build version code and start testing the major features of the application to ensure that all the functionality is working as expected or not by following the phases&#x20;

* One-step Installation - Positive Scenarios to be executed
* API karate Framework - Calling Spec , dimension , Ingestion, and Schedule APIs for each program wise to verify able to add schemas to db , input files to buckets, and verify the ability to schedule the Nifi processor and validate the processing of the ingested input files&#x20;
* Verify the after Nifi Processing of the files whether datasets of all the programs have been created tables or not in the database&#x20;
* Verifying the Visualization&#x20;
* Login Page&#x20;
* Dashboard - Summary Statistics&#x20;
* All Program Dashboard - Data is showing up or not, and each web feature functionality is working as expected or not
