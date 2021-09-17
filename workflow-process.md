# Workflow process

cQube workflow consists mainly two parts

1. Data emission
2. Data processing

**Data emission:** Data from the state education system will be emitted into the S3 emission bucket/data folder using the cQube data emission API.

**Data processing:** NIFI is the central orchestration system which handles the complete workflow process and generates JSON files. These JSON files are used for the visualisation reports. The [architecture diagram](https://app.gitbook.com/@sunbird/s/cqube/cqube-software-architecture) will give more clarity on the data processing.  


