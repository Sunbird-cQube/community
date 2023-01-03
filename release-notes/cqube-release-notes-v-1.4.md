---
description: Release Version 1.4,  29 September 2020
---

# cQube - Release Notes V 1.4

**1.** **Objectives of the cQube release 1.4**

cQube release version 1.4, as an upgrade to the cQube release 1.3 has been updated with new reporting features using periodic exam data and reports using composite data.

cQube release version 1.4.1 is an intermediate release in which UI related changes have been added in the cQube application.

**2.** **Scope**

cQube product release features and issues are described in this version 1.4 and 1.4.1. This release contains a map based report for the periodic exam data and scatter plot chart for the composite data. The release 1.4.1 consists of UI changes in the login screen and the landing page.

**3.** **Summary of the Product Features**&#x20;

This document contains information on the following new features and enhancements to the existing features of the cQube product:

1. Map based visualization for the periodic exam data
2. Scatter plot visualization using the composite data.
3. Enhancements for UDISE data related screens:
   1. Rank implementation changes
   2. UDISE summary screen
4. The following issues from the previous release have been resolved:
   1. Validations for all tables
   2. Nifi restart issue
5. Upgradation from release 1.3 to 1.4
6. Release 1.4.1
   1. UI changes in the login screen and the landing page
   2. Diksha column chart - addition of percentage values

**4.** **Description of the Product Features**

1\. Periodic Exam Data Visualization

[CQB-567](https://project-sunbird.atlassian.net/browse/CQB-567), [CQB-568](https://project-sunbird.atlassian.net/browse/CQB-568), [CQB-569](https://project-sunbird.atlassian.net/browse/CQB-569), [CQB-570](https://project-sunbird.atlassian.net/browse/CQB-570), [CQB-571](https://project-sunbird.atlassian.net/browse/CQB-571), [CQB-572](https://project-sunbird.atlassian.net/browse/CQB-572), [CQB-573](https://project-sunbird.atlassian.net/browse/CQB-573)

| Sl No. | Feature          | Description                                                                                                                                                                            | Roles Impacted        |
| ------ | ---------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------- |
| 1      | Map based report | <p>Map based reports, districtwise, blockwise and clusterwise have been created for the following metrics:     </p><p>- Performance</p><p>- Academic Year</p><p>- Grades          </p> | Admin, Report viewers |

2\. Composite Data Visualization

[CQB-575](https://project-sunbird.atlassian.net/browse/CQB-575), [CQB-590](https://project-sunbird.atlassian.net/browse/CQB-590), [CQB-578](https://project-sunbird.atlassian.net/browse/CQB-578), [CQB-579](https://project-sunbird.atlassian.net/browse/CQB-579)

| Sl No. | Feature      | Description                                                                                                                                                                                                                                                                                                                                                                              | Roles Impacted        |
| ------ | ------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------- |
| 1      | Scatter plot | <p>Composite report is the combination of multiple existing reports and creating the scatter plot visualisation based on the metrics derived for individual reports.</p><p>Composite report = Attendance report metrics, PAT report metrics, Diksha report metrics and few other sources. (Metrics like → Administration,Arts Lab,Teacher Profile,Total Content Plays- Textbook etc)</p> | Admin, Report viewers |

3\. Enhancements to UDISE related screens

[CQB-581](https://project-sunbird.atlassian.net/browse/CQB-581),  [CQB-582](https://project-sunbird.atlassian.net/browse/CQB-582)

| Sl No. | Feature                     | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     | Roles Impacted        |
| ------ | --------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------- |
| 1      | Rank implementation changes | <p>Udise rank should be displayed as follows in the tool tip:</p><p><strong>At district level:</strong></p><p>Rank of the district within the state.</p><p><strong>At block level:</strong></p><p>Rank of the block within the state.</p><p>Rank of the block within the district.</p><p><strong>At Cluster level:</strong></p><p>Rank of the cluster within the state.</p><p>Rank of the cluster within the district.</p><p>Rank of the cluster within the block.</p><p><strong>At school level:</strong></p><p>Rank of the school within the state.</p><p>Rank of the school within the district.</p><p>Rank of the school within the block.</p><p>Rank of the school within the cluster.</p> | Admin, Report viewers |
| 2      | UDISE Summary Screen        | The data processing statuses like: Null validation, column validation, duplicate validation are available in the summary statistics for all the 32 udise input tables.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          | Admin, Report viewers |

4\. Resolutions to issues from the previous release

[CQB-561](https://project-sunbird.atlassian.net/browse/CQB-561), [CQB-562](https://project-sunbird.atlassian.net/browse/CQB-562)

| Sl No. | Feature                        | Description                                                                                                                                       | Roles Impacted        |
| ------ | ------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------- |
| 1      | Nifi validation for all tables | Nifi was not validating the Infrastructure columns from the emission file. Validations have been handled.                                         | Admin, Report viewers |
| 2      | Nifi restart issue             | <p>Nifi was restarting unexpectedly. This issue was only while processing the semester data file.</p><p>This has been solved in this release.</p> | Admin, Report viewers |

5\. Upgradation from release 1.3 to release 1.4

[CQB-574](https://project-sunbird.atlassian.net/browse/CQB-574)

| Sl No. | Feature                           | Description                                                                                                                                                        | Roles Impacted        |
| ------ | --------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ | --------------------- |
| 1      | Upgradation Tasks for release 1.4 | <p>Integration of Periodic Test Report - Ansible Development</p><p>Unit testing</p><p>Integration of composite report - Ansible Development</p><p>Unit testing</p> | Admin, Report viewers |

6\. Release 1.4.1

[CQB-628](https://project-sunbird.atlassian.net/browse/CQB-628), [CQB-624](https://project-sunbird.atlassian.net/browse/CQB-624)

| Sl No. | Feature             | Description                                         | Roles Impacted        |
| ------ | ------------------- | --------------------------------------------------- | --------------------- |
| 1      | UI Changes          | UI changes in the login screen and the landing page | Admin, Report viewers |
| 2      | Diksha column chart | Addition of percentage values to the column chart   | Admin, Report viewers |

**5.** **Known Issues:**

This is a section that describes all the known issues/ bugs that are present in the cQube product and they have been reported as being a part of this release.

| Sl No | Issues                                                                                                                                                                                                                                                                                                                                      |
| ----- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1     | NIFI Restart issue - NIFI is restarting when the data is progressing due to the heap memory. But it is not effect on the data process [CQB-562](https://project-sunbird.atlassian.net/browse/CQB-562)                                                                                                                                       |
| 2     | Telemetry component starting issue -  After the installation & Upgradation few of the processes are not starting in the Telemetry processor group. This issue occurred after changing the telemetry to run forever. It was working fine when the processor group restarted. [CQB-620](https://project-sunbird.atlassian.net/browse/CQB-620) |
