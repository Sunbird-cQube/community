---
description: Release Version 2 - 11 June 2021
---

# cQube - Release V 2

**1.** **Objectives of the cQube release 2.0**

The cQube release version 2.0 divides cQube into a base installation section and the cQube workflow. Installation is split into two sections, a base cQube installation which installs all the software components and the workflow installation configures the workflow, installs data processing components, SQL queries and the database components.

**2.** **Scope**

cQube product release features and issues are described in this version 2.0. and contains a description of the functionalities that have been developed/ upgraded in this version.

**3.** **Summary of the Product Features**&#x20;

This document contains information on the following new features and enhancements to the existing features of the cQube product:

●        cQube base & cQube workflow installation/upgradation separation - cQube Base Installation/upgradation

●        cQube base & cQube workflow installation/upgradation separation - cQube Workflow Installation/upgradation

●        Diksha summary rollup performance

●        Data retention for transaction table based on the configured duration

●        Performance benchmark

●        Defect fixes - CRC nifi special character issue handling

●        Defect fixes - composite report and diksha progress report

**4.** **Description of the Product Features**

1\. cQube Base Installation/upgradation

&#x20;[CQB-1145](https://project-sunbird.atlassian.net/browse/CQB-1145)

| Sl No. | Feature                              | Description                                                                                                                                                                                                                                                                                                                                                                        | Roles Impacted        |
| ------ | ------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------- |
| 1      | cQube base Installation/ upgradation | <p>This feature includes the following -</p><p>- Installation of  the cQube base data path</p><p>- Installation and configuration of all the software components required in the cQube product</p><p>Note: This installation does not include installation of any tables. None of the NIFI processes will be created</p><p>- Upgradation process is also part of the same base</p> | Admin, Report viewers |

2\. cQube Workflow Installation/upgradation

[CQB-1146](https://project-sunbird.atlassian.net/browse/CQB-1146)

| Sl No. | Feature                                  | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  | Roles Impacted        |
| ------ | ---------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------- |
| 1      | cQube workflow Installation/ Upgradation | <p>The base installation installs all the base software components and this installation takes place over the base installation</p><p>This installation configures the workflow, installs data processing components, SQL queries. This installation creates tables, creates functions, creates views and materialized views.</p><p>This installation also installs the NIFI processes, imports nifi templates, updates nifi parameters and initializes nifi controllers</p><p>There will ne workflow upgradation at all future releases</p> | Admin, Report viewers |

3\. Diksha summary rollup performance

[CQB-1142](https://project-sunbird.atlassian.net/browse/CQB-1142)

| Sl No. | Feature        | Description                                                                                                                                                                                                                                                                                        | Roles Impacted        |
| ------ | -------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------- |
| 1      | Diksha summary | <p>The diksha summary rollup nifi data flow has been optimized. </p><p>All files related to a request have been loaded into temp and a single workflow is initiated.</p><p>Month wise aggregation table is created to improve the query performance.</p><p>The overall query table is updated.</p> | Admin, Report viewers |

4\. Data retention for transaction table based on the configured duration

[CQB-1143](https://project-sunbird.atlassian.net/browse/CQB-1143)

| Sl No. | Feature        | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       | Roles Impacted        |
| ------ | -------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------- |
| 1      | Data retention | <p>Data retention has been set up for the following data sources.</p><p>-          Periodic Assessment</p><p>-          Semester Assessment</p><p>-          CRC</p><p>-          Diksha summary rollup</p><p>The default data retention time period for all the above tables is set to 90 days</p><p>The retention time period is configurable using the data replay/retention screen that has been provided in the admin console.</p><p>The data in the transaction tables will be deleted based on the retention time set.</p> | Admin, Report viewers |

5\. Security vulnerabilities fixes

[CQB-1147](https://project-sunbird.atlassian.net/browse/CQB-1147)

| Sl No. | Feature        | Description                                                                                                                                                                | Roles Impacted        |
| ------ | -------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------- |
| 1      | Security fixes | <p>The following defects have been fixed in this release:</p><p>- CRC nifi special character issue handling</p><p>- composite report and diksha progress report issues</p> | Admin, Report viewers |
