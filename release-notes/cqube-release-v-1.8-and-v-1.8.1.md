---
description: Release Version 1.8 - 24 December 2020, Version 1.8.1 - 31 December 2020
---

# cQube - Release V 1.8 and V 1.8.1

**1.** **Objectives of the cQube release 1.8, 1.8.1**

cQube release version 1.8, as an upgrade to the cQube release 1.7 has health card indices to view the health of a location.  This release has enhancements to TPD reports and PAT heatmaps.

**2.** **Scope**

cQube product release features and issues are described in this version 1.8. This release has enhancements on TPD reports and PAT heatmaps and a new functionality, health card which can be used to view the health of a location with respect to attendance, infrastructure and assessment.

**3.** **Summary of the Product Features**&#x20;

This document contains information on the following new features and enhancements to the existing features of the cQube product:

1. Health card Index
2. Enhancements to existing reports
   1. Pagination in heatmap
   2. Display indicator wise metrics in PAT heatmap
   3. Configuration of infra weights API
   4. Multiple select for list of courses and districts in TPD course progress report
3. Release 1.8.1
4. Diksha TPD UUID mapping implementation

**4.** **Description of the Product Features**

1\. Health card index

&#x20;[CQB-838](https://project-sunbird.atlassian.net/browse/CQB-838)

| Sl No. | Feature           | Description                                                                                                                                                                                                                                | Roles Impacted        |
| ------ | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | --------------------- |
| 1      | Health card index | Health card index contains health index of Student attendance, Student semester, CRC visits, Udise, PAT performance at the school level, Health card index cluster level, Health card index block level, Health card index district level. | Admin, Report viewers |

2\. Enhancements to the existing reports

[CQB-823](https://project-sunbird.atlassian.net/browse/CQB-823), [CQB-824](https://project-sunbird.atlassian.net/browse/CQB-824), [CQB-825](https://project-sunbird.atlassian.net/browse/CQB-825), [CQB-826](https://project-sunbird.atlassian.net/browse/CQB-826)&#x20;

| Sl No. | Feature                             | Description                                                                                                                                                                                                                                                                                      | Roles Impacted        |
| ------ | ----------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | --------------------- |
| 1      | Enhancements to PAT and TPD reports | <p>Pagination has been implemented in the heatmap</p><p>Indicator wise metrics are being displayed in the PAT heatmap</p><p>Api for the configuration of infra weights</p><p>Multiple select option has been implemented for the list of courses and districts in TPD course progress report</p> | Admin, Report viewers |

7\. Release 1.8.1

[CQB-851](https://project-sunbird.atlassian.net/browse/CQB-851), [CQB-852](https://project-sunbird.atlassian.net/browse/CQB-852), [CQB-853](https://project-sunbird.atlassian.net/browse/CQB-853), [CQB-854](https://project-sunbird.atlassian.net/browse/CQB-854), [CQB-855](https://project-sunbird.atlassian.net/browse/CQB-855)

| Sl No. | Feature                                | Description                                                                                                                                                                                                                                              | Roles Impacted        |
| ------ | -------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------- |
| 1      | Health card                            | <ol><li>Details of School level Information was cleaned</li><li>Removed the info card color and added the color coding as a circular marker at the card heading</li><li>Tooltip Information was sorted, details were cleaned and  categorised.</li></ol> | Admin, Report viewers |
| 2      | Static tables configuration            | Static tables were configured as UDISE / State specific                                                                                                                                                                                                  | Admin, Report viewers |
| 3      | Diksha TPD UUID mapping implementation | Diksha TPD UUID mapping implementation to get the school\_id of the users.                                                                                                                                                                               | Admin, Report viewers |

**5.** **Known Issues:**

This is a section that describes all the known issues/ bugs that are present in the cQube product and they have been reported as being a part of this release.

| Sl No | Issues                                                                                                                        |
| ----- | ----------------------------------------------------------------------------------------------------------------------------- |
| 1     | Maximum 1000 files are displayed in S3 bucket admin console - [CQB-864](https://project-sunbird.atlassian.net/browse/CQB-864) |
| 2     | Progress-exhaust, Summary-rollup summary screen issue [CQB-863](https://project-sunbird.atlassian.net/browse/CQB-863)         |
