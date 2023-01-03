---
description: Release Version 1.13 - 12 May 2021, Version 1.13.1 - 20 May 2021
---

# cQube - Release V 1.13 and V 1.13.1

**1.** **Objectives of the cQube release 1.13 and 1.13.1**

cQube release version 1.13, as an upgrade to the cQube release 1.12 includes periodic assessment query performance, semester attendance query performance and student attendance query performance  optimization.  Release 1.13.1 is a patch release for the cQUbe version 1.13.1 with improvements in PAT performance and updates to the PAT LO table .

**2.** **Scope**

cQube product release features and issues are described in this version 1.13 and 1.13.1. This document contains a short description of performance optimizations implemented..

**3.** **Summary of the Product Features**&#x20;

This document contains information on the following new features and enhancements to the existing features of the cQube product:

●        Periodic assessment query performance optimization

●        Semester assessment query performance optimization

●        Student attendance query performance optimization

●        UI Changes

○        Removal of the Diksha TPD teachers percentage report

○        Addition of enrolment and completion number in the tooltip for TPD Total Enrolments /Completion

○        Move the Exception Segment at the very end in the cQube home page dashboards

○        Addition of Color indicators to all the heatmap reports

○        Addition of cell color and tooltip in PAT LO table

●        Release 1.13.1

○        PAT performance improvement

○        Update to PAT LO table with percentage instead of marks

○        Defect fixes - composite report and diksha progress report

**4.** **Description of the Product Features**

1\. Periodic assessment query performance optimization

&#x20;[CQB-1102](https://project-sunbird.atlassian.net/browse/CQB-1102)

| Sl No. | Feature             | Description                                                            | Roles Impacted        |
| ------ | ------------------- | ---------------------------------------------------------------------- | --------------------- |
| 1      | Periodic Assessment | The performance of the periodic assessment queries have been optimized | Admin, Report viewers |

2\. Semester assessment query performance optimization

[CQB-1103](https://project-sunbird.atlassian.net/browse/CQB-1103)

| Sl No. | Feature             | Description                                                                            | Roles Impacted        |
| ------ | ------------------- | -------------------------------------------------------------------------------------- | --------------------- |
| 1      | Semester assessment | The performance of the semester assessment queries have been optimized in this release | Admin, Report viewers |

3\. Student attendance query performance optimization

[CQB-1104](https://project-sunbird.atlassian.net/browse/CQB-1104)

| Sl No. | Feature            | Description                                                                 | Roles Impacted        |
| ------ | ------------------ | --------------------------------------------------------------------------- | --------------------- |
| 1      | Student attendance | The student attendance query performance has been optimized in this release | Admin, Report viewers |

4\. UI Changes

[CQB-1106](https://project-sunbird.atlassian.net/browse/CQB-1106), [CQB-1107](https://project-sunbird.atlassian.net/browse/CQB-1107), [CQB-1108](https://project-sunbird.atlassian.net/browse/CQB-1108), [CQB-1109](https://project-sunbird.atlassian.net/browse/CQB-1109), [CQB-1110](https://project-sunbird.atlassian.net/browse/CQB-1110)

| Sl No. | Feature                                                                                                | Description                                                                                                                                                                                                      | Roles Impacted        |
| ------ | ------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------- |
| 1      | Removal of the Diksha TPD teachers percentage report                                                   | As we don’t have the proper details of the intended audience who will be applicable for the course, Find no usage of this report.                                                                                | Admin, Report viewers |
| 2      | Addition of enrolment and completion number in the tooltip for TPD Total Enrolments /Completion report | Addition of the enrolment and completion number in the tooltip will provide the user to understand the difference between enrolment and completion clearly                                                       | Admin, Report viewers |
| 3      | Move the Exception Segment at the very end in the cQube home page dashboards                           | As a logical segment division, moved the Exception reports to the end of home page dashboards.                                                                                                                   | Admin, Report viewers |
| 4      | Addition of Color indicators to all the heatmap reports                                                | As user perspective, Added the static indicators for better understanding color codes of the heatmap cells                                                                                                       | Admin, Report viewers |
| 5      | Addition of cell color and tooltip in PAT LO table                                                     | <p>Due to the more benefits like sorting, cell adjustments, changed the LO table to replicate the heatmap functionality.</p><p>In the LO table report added the color coding and tooltip to the table cells.</p> | Admin, Report viewers |

5\. Release 1.13.1

[CQB-1120](https://project-sunbird.atlassian.net/browse/CQB-1120), [CQB-1121](https://project-sunbird.atlassian.net/browse/CQB-1121), [CQB-1122](https://project-sunbird.atlassian.net/browse/CQB-1122), [CQB-1123](https://project-sunbird.atlassian.net/browse/CQB-1123), [CQB-1124](https://project-sunbird.atlassian.net/browse/CQB-1124), [CQB-1125](https://project-sunbird.atlassian.net/browse/CQB-1125), [CQB-1126](https://project-sunbird.atlassian.net/browse/CQB-1126)

| Sl No. | Feature      | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                              | Roles Impacted        |
| ------ | ------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | --------------------- |
| 1      | PAT Report   | PAT report performance has been improved while writing the reports into an output file                                                                                                                                                                                                                                                                                                                                                                                   | Admin, Report viewers |
| 2      | PAT LO Table | The PAT LO table currently contains percentages instead of marks. The marks have been provided in the tooltip                                                                                                                                                                                                                                                                                                                                                            |                       |
| 3      | Defect fixes | <p>1. Diksha API progress call - multiple requests were being made whenever there was a failure.</p><p>Once the diksha request is successful, multiple requests should not be made whenever there is a failure during processing in cQube. This issue has been resolved in this release.</p><p>2. Composite report issue  - Total number of schools was not being displayed based on the school management option selected, which has been resolved in this release.</p> |                       |

**5.** **Known Issues:**

This is a section that describes all the known issues/ bugs that are present in the cQube product and they have been reported as being a part of this release.

| Sl No | Issues                                                                                                                                                                               |
| ----- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 1     | Periodic Assessment Test LO Table, when there are few records in the table tooltip is not shown for a few cells. - [CQB-1101](https://project-sunbird.atlassian.net/browse/CQB-1101) |
