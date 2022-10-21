# cQube - Release V 4.0-beta

#### Document Release Version


|Project    |Release Date    |Release Version|
|---------|----------------|------------------|
|cQube    | 21 Oct 2022 |V 4.0-beta    |

## Overview

cQube v4.0-beta  has improved features and bug fixes.

## Insatallation Features from cqube-4.0-alpha
[Installation process](https://github.com/Sunbird-cQube/cQube_Edu/blob/cqube-v4.0-beta/README.md)

## Upgradation Features from cqube-4.0-alpha

[Upgrade process](https://github.com/Sunbird-cQube/cQube_Edu/blob/cqube-v4.0-beta/README.md)

## New Features Included

**1. Database backup**

User can configure the DB backup during Installation.
Based on the configuration, the database(Postgre DB) will be backed up and stored in input storage (supported storages are aws s3, azure blob storage and on-premise).

For more details refer the below link 

[Databse backup document](https://drive.google.com/u/1/open?id=15sWXbn5efRZG8WnV9U89pCDwbj1jKlUK)

**2. Download Report option.**

**3. Full screen option for charts.**

**4. Summary statistics for all the existing datasoruces.**

**5. Visualization app's footer timestamp are dynamic.**

**6. Supported storage types are aws s3 and azure blob storage**

**7. New Datasource can be added/configured**


Follow the below mentioned link for step by step process to add new datasource and the limitations.

[Data source configuration guideline document](https://drive.google.com/u/1/open?id=1gSJSQCOLG0wsWeBDq8T2a8F3n_kCJORU8hsPuaaGG-c)

[Sample datasource configuration files](https://drive.google.com/u/1/open?id=1WkMA_xOUp3ywta_baEtjPqc7GCg24v7aZuHp07zgcGM)


In-built Dashboards supports configuration to enable or disable.

Below are the list of dashboards/data sources.

1. School Infrastructure
2. Student Performance
3. Attendance
4. Courses
5. Energised Textbook Usage
6. Other Diksha Metrics
7. CRC Visit
8. Composite reports across metrics
9. Progress card
10. Exception List
11. Telemetry

    [configuration file to enable/disable the above 11 datasources](https://github.com/Sunbird-cQube/cQube_Edu/blob/cqube-v4.0-beta/devops/datasource_config.yml)

12. Nishtha
13. Diksha-ETB
14. Micro-Improvements
15. PM Poshan
16. NAS
17. UDISE+
18. PGI
19. Nipun Bharat
20. NCERT Quiz
21. NCF

Above 10(12 to 20) datasources supports Report configuration

The user has to provide information like data source name, schema details of the data source individually. And also the information includes aggregation, grouping information, and inputs required to generate the reports such as dimensions required, tooltip information, filters to be considered and displayed for the report etc.,. Once the user has provided the necessary details in the data and report configurations all of the reports will get generated automatically and will be displayed in the web application.

[Report configuration files](https://github.com/Sunbird-cQube/cQube_Edu/tree/cqube-v4.0-beta/apis/node-api/core/config/state)

[To enable or disable the data source use this file](https://drive.google.com/u/1/open?id=1fAq9I5ro4RC7IEoocaSwCKd3ArPA1gwp5-hAhuyMQQ0)

**8. when the user is on the scanning page/OTP page if he does the refresh then he will navigate to the login screen**


All the dashboards in cqube expects the input files in .zip format. For more details on input files and its format refer the below.

Below mentioned dashboards, and it's input files should be in .csv format( ',' is the delimiter) and compressed into .zip format.
1.  Courses
2.  Energised Textbook Usage
3.  Other Diksha Metrics
4.  Nishtha
5.  Diksha-ETB
6.  Micro-Improvements
7.  PM Poshan
8.  NAS
9.  UDISE+
10.  PGI
11.  Nipun Bharat
12.  NCERT Quiz
13.  NCF

Below mentioned dashboards, and it's input files should be in .csv format( '|' is the delimiter) and compressed into .zip format.
1. School Infrastructure
2. Student Performance
3. Attendance


## Bug Fixes

[Bug fixes](https://github.com/orgs/Sunbird-cQube/projects/5/views/3?filterQuery=label%3A%22From-v4.0-Alpha%22+status%3A%22QA+Complete+%F0%9F%91%8C%F0%9F%8F%BD%22)