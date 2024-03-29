---
description: Release Version 1.12 - 31 March 2021, Version 1.12.1 - 22 April 2021
---

# cQube - Release V 1.12 and V 1.12.1

**1.** **Objectives of the cQube release 1.12 and 1.12.1**

cQube release version 1.12, as an upgrade to the cQube release 1.12 includes school management selection, trend line charts, time range selection implementation for PAT map report and CRC reports.  The release version 1.12.1 consists of upgrades to the tasks completed in the release 1.12.

**2.** **Scope**

cQube product release features and issues are described in this version 1.12 and 1.12.1. This document contains a short description of the time range implementation, trend line charts and enhancements to the cQube product.

**3.** **Summary of the Product Features**&#x20;

This document contains information on the following new features and enhancements to the existing features of the cQube product:

●        Time selection implementation

○        CRC Report

○        PAT map based report

●        School management selection

●        Trend Line charts for student attendance report

●        Progress card update - CRC visits in the progress card is displayed based on the ‘number of visits’ instead of ‘no visits’

●        Nifi upgradation to the latest stable version

●        School Management selection in trends chart

●        Footer in trends chart

●        Pagination in table reports

●        Release version 1.12.1

○           Addition of total no. of Students, Total schools in PAT Map report & Heatmap tooltip

○           Addition of the Total Students, Total schools in PAT Map report footer

○           Addition of the Total Students, Total schools in SAT Map report & Heatmap tooltip

○           Addition  of the Total Students, Total schools in SAT Map report footer

○           Addition of the Pagination & Search functionality to the table reports

○           Enabled the school level metrics in CRC Report

**4.** **Description of the Product Features**

1\. Time selection implementation

&#x20;[CQB-1037](https://project-sunbird.atlassian.net/browse/CQB-1037), [CQB-1049](https://project-sunbird.atlassian.net/browse/CQB-1049)

| Sl No. | Feature                   | Description                                                                                                                           | Roles Impacted        |
| ------ | ------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- | --------------------- |
| 1      | Time range implementation | <p>Time range selection has been implemented for the following:</p><p>-          CRC report</p><p>-          PAT map based report</p> | Admin, Report viewers |

2\. School Management selection

[CQB-1034](https://project-sunbird.atlassian.net/browse/CQB-1034)

| Sl No. | Feature                     | Description                                                                                                                                                                              | Roles Impacted        |
| ------ | --------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------- |
| 1      | School management selection | <p>Select ‘school management type’ selection box has been added to the home page.</p><p>School management selection option has been implemented to all reports except Diksha reports</p> | Admin, Report viewers |

3\. Trend line charts for student attendance report

[CQB-1038](https://project-sunbird.atlassian.net/browse/CQB-1038)

| Sl No. | Feature                                        | Description                                                                                                                                                 | Roles Impacted        |
| ------ | ---------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------- |
| 1      | Trend line chart for student attendance report | A hyperlink with ‘Access to trends’ has been provided for the student attendance chart. The report shows the attendance trends across districts in a state. | Admin, Report viewers |

4\. Progress card update - CRC visits

[CQB-1038](https://project-sunbird.atlassian.net/browse/CQB-1038)

| Sl No. | Feature                             | Description                                                                                                                          | Roles Impacted        |
| ------ | ----------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ | --------------------- |
| 1      | Progress card update for CRC visits | Progress card update - CRC visits in the progress card is now being displayed based on the ‘number of visits’ instead of ‘no visits’ | Admin, Report viewers |

5\. Nifi upgradation to the latest stable version

[CQB-1038](https://project-sunbird.atlassian.net/browse/CQB-1038)

| Sl No. | Feature          | Description                                                                                                                                                                                                                                 | Roles Impacted        |
| ------ | ---------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------- |
| 1      | Nifi upgradation | <p>Nifi should be upgraded to the latest stable version. The cQube product configurations should be changed according to the latest version of NIFI.</p><p>This nifi upgradation functionality has been implemented in the release 1.12</p> | Admin, Report viewers |

6\. School Management selection in trends chart

[CQB-1089](https://project-sunbird.atlassian.net/browse/CQB-1089)

| Sl No. | Feature                     | Description                                                                                 | Roles Impacted        |
| ------ | --------------------------- | ------------------------------------------------------------------------------------------- | --------------------- |
| 1      | School Management selection | -             School management selection option has been added to the trends charts report | Admin, Report viewers |

7\. Pagination in Table reports

&#x20;[CQB-1090](https://project-sunbird.atlassian.net/browse/CQB-1090)

| Sl No. | Feature                     | Description                                                                                                                                                   | Roles Impacted        |
| ------ | --------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------- |
| 1      | Pagination in Table reports | <p>-             Pagination has been added to the below Table reports</p><p>-          Usage by Course content</p><p>-          Usage by Textbook Content</p> | Admin, Report viewers |

8\. Footer in trends chart

[CQB-1091](https://project-sunbird.atlassian.net/browse/CQB-1091)

| Sl No. | Feature                | Description                                              | Roles Impacted        |
| ------ | ---------------------- | -------------------------------------------------------- | --------------------- |
| 1      | Footer in trends chart | -             Footer has been added to the trends charts | Admin, Report viewers |

9\. Release version 1.12.1

[CQB-1093](https://project-sunbird.atlassian.net/browse/CQB-1093), [CQB-1094](https://project-sunbird.atlassian.net/browse/CQB-1094), [CQB-1095](https://project-sunbird.atlassian.net/browse/CQB-1095), [CQB-1096](https://project-sunbird.atlassian.net/browse/CQB-1096), [CQB-1097](https://project-sunbird.atlassian.net/browse/CQB-1097)

| Sl No. | Feature                          | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               | Roles Impacted        |
| ------ | -------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------- |
| 1      | Tasks for release version 1.12.1 | <p>- Addition of total no. of Students, Total schools in PAT Map report &#x26; Heatmap tooltip</p><p>- Addition of the Total Students, Total schools in PAT Map report footer</p><p>- Addition of the Total Students, Total schools in SAT Map report &#x26; Heatmap tooltip</p><p>- Addition  of the Total Students, Total schools in SAT Map report footer</p><p>- Addition of the Pagination &#x26; Search functionality to the table reports</p><p>Enabled the school level metrics in CRC Report</p> | Admin, Report viewers |

**5.** **Known Issues:**

This is a section that describes all the known issues/ bugs that are present in the cQube product and they have been reported as being a part of this release.

| Sl No | Issues |
| ----- | ------ |
|       |        |
