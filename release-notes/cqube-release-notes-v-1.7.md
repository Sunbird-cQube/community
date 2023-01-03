---
description: Release Version 1.7 - 08 December 2020
---

# cQube - Release Notes V 1.7

**1.** **Objectives of the cQube release 1.7**

cQube release version 1.7, as an upgrade to the cQube release 1.6, has TPD reports, load balancer changes from ELB to ALB, NIFI scheduler and state specific configurations.

**2.** **Scope**

cQube product release features and issues are described in this version 1.7. This release has enhancements on Diksha API test with real data, load balancer changes from ELB to ALB, Nifi Scheduler for Daily, Weekly, Monthly and Yearly and state specific configurations.

**3.** **Summary of the Product Features**&#x20;

This document contains information on the following new features and enhancements to the existing features of the cQube product:

1. Load balancer changes from ELB to ALB
2. Nifi Scheduler for Daily, Weekly, Monthly and Yearly
3. State specific configurations
4. State specific Static table configurations from UDISE data
5. Diksha TPD Enrolment/Completion reports
6. API Token based authentication
7. Configuration of session out time
8. Configuration of Diksha Columns

**4.** **Description of the Product Features**

1\. Load balancer changes from ELB to ALB

&#x20;[CQB-761](https://project-sunbird.atlassian.net/browse/CQB-761)

| Sl No. | Feature              | Description                                                                      | Roles Impacted |
| ------ | -------------------- | -------------------------------------------------------------------------------- | -------------- |
| 1      | Load balancer change | -          Migration from AWS Classic Load Balancer to Application Load Balancer |                |

2\. Nifi scheduler frequency

[CQB-743](https://project-sunbird.atlassian.net/browse/CQB-743)

| Sl No. | Feature        | Description                                                                                   | Roles Impacted        |
| ------ | -------------- | --------------------------------------------------------------------------------------------- | --------------------- |
| 1      | Nifi scheduler | -          Nifi scheduler has been added the option to set Daily, Weekly, Monthly and Yearly. | Admin, Report viewers |

3\. State specific configurations&#x20;

[CQB-762](https://project-sunbird.atlassian.net/browse/CQB-762)

| Sl No. | Feature                       | Description                                                                                                                                         | Roles Impacted        |
| ------ | ----------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------- |
| 1      | State specific configurations | <p>-          Add the state specific configurations at installation</p><p>-          State selection added for the cQube 1.7 upgrade from 1.6.1</p> | Admin, Report viewers |

4\. State specific Static table configurations from UDISE data

[CQB-764](https://project-sunbird.atlassian.net/browse/CQB-764)

| Sl No. | Feature                             | Description                                                                                                                                                                                                                                                                                                      | Roles Impacted        |
| ------ | ----------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------- |
| 1      | State specific table configurations | <p>-          Changing of static tables using UDISE data from state specific static tables</p><p>-          Validations need to be done using UDISE data structure for district_mst,block_mst,cluster_mst,school_mst</p><p>-          All the metrics calculation should be updated based on the UDISE data.</p> | Admin, Report viewers |

5\. Diksha TPD Enrolment/Completion reports

[CQB-752,](https://project-sunbird.atlassian.net/browse/CQB-752) [CQB-766](https://project-sunbird.atlassian.net/browse/CQB-766)

| Sl No. | Feature             | Description                                                                                                                                                 | Roles Impacted        |
| ------ | ------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------- |
| 1      | Nifi process status | <p>-          New report, Diksha TPD Enrolment/Completion report is added</p><p>-          New report, Diksha TPD Completion Percentage Report is added</p> | Admin, Report viewers |

6\. Upgradation from release 1.6.1 to 1.7

[CQB-768](https://project-sunbird.atlassian.net/browse/CQB-768)

| Sl No. | Feature                               | Description                                                                                                                                                                                                                                                                                                                                                                         | Roles Impacted        |
| ------ | ------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------- |
| 1      | Upgradation from release 1.6.1 to 1.7 | <p>-          Ansible code added for the upgradation from release 1.6.1 to 1.7</p><p>-          State specific configurations were added</p><p>-          Diksha columns configuration were added</p><p>-          Session timeout was changed to default 7 days, minimum timeout 30 Minutes and maximum timeout period is 3650 days</p><p>-          Kong API gateway is added</p> | Admin, Report viewers |

7\. API Token based authentication

[CQB-808](https://project-sunbird.atlassian.net/browse/CQB-808)

| Sl No. | Feature                        | Description                                                                                                                                                                                                                                                                                      | Roles Impacted        |
| ------ | ------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | --------------------- |
| 1      | API token based authentication | <p>-          Token based authentication using Kong gateway.</p><p>-          Emission user creation was modified with the token creation at admin console “Create User” page.</p><p>-           The configurations have been updated by ansible during the installation &#x26; upgradation.</p> | Admin, Report viewers |

7\. Configuration of session out time

[CQB-807](https://project-sunbird.atlassian.net/browse/CQB-807)

| Sl No. | Feature                           | Description                                                                                                                                                                                                                                                                                                        | Roles Impacted        |
| ------ | --------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | --------------------- |
| 1      | Configuration of session out time | <p>-          Configuration of the access_token life span for the cQube Active session.</p><p>-          Session timeout was changed to default 7 days, minimum timeout 30 Minutes and maximum timeout period is 3650 days</p><p>-          Session time specified during the installation &#x26; upgradation.</p> | Admin, Report viewers |

8\. Configuration of diksha columns

[CQB-809](https://project-sunbird.atlassian.net/browse/CQB-809)

| Sl No. | Feature                         | Description                                                                                                                                                                                                                                                                                                                                                                                                                             | Roles Impacted        |
| ------ | ------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------- |
| 1      | Configuration of diksha columns | <p>-          The diksha columns can be configured during the installation &#x26; upgradation stage.</p><p>-          Nifi side validations can be done if the columns are available</p><p>-          Metrics are calculated according to the column's availability.</p><p>-          If the columns are not available, Diksha “Usage by user profile” report will be disabled  from the dashboard else the report will be enabled.</p> | Admin, Report viewers |

**5.** **Known Issues:**

This is a section that describes all the known issues/ bugs that are present in the cQube product and they have been reported as being a part of this release.

| Sl No | Issues                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| ----- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1     | Nifi scheduler issue - Nifi schedulers were pointed to the scheduler names instead of IDs as Ids are refreshing at upgradation. For 1.7 we must do the manual scheduling and it will work with the auto schedules. [CQB-800](https://project-sunbird.atlassian.net/browse/CQB-800)                                                                                                                                                                        |
| 2     | <p>Usage by course content Report - Sorting issue</p><p>Classes like Class 3, Class 4 need to be added '0' before the number at the input data. then the sorting order will be fixed.</p><p>Ex: Class 10, Class 3 and Class 4, First system is considered Class after then will check for the number. As 3 and 4 are bigger than 1, Class 10 is coming at the wrong place. <a href="https://project-sunbird.atlassian.net/browse/CQB-814">CQB-814</a></p> |
