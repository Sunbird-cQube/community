---
description: Release Version 1.6 - 06 November 2020, Version 1.6.1 - 13 November 2020
---

# cQube - Release Notes V 1.6 and V 1.6.1

&#x20;**1.** **Objectives of the cQube release 1.6 and 1.6.1**

cQube release version 1.6, as an upgrade to the cQube release 1.5 has enhancements to the PAT reports and diksha reports.

Release 1.6.1 is an amendment release in which changes have been added to the existing reports. Api certification has been implemented in this release.

**2.** **Scope**

cQube product release features and issues are described in this version 1.6. This release has enhancements to PAT reports, diksha reports. Other functions included in this release are diksha API integration, API certification and Nifi process optimization.

**3.** **Summary of the Product Features**&#x20;

This document contains information on the following new features and enhancements to the existing features of the cQube product:

1. PAT reports
   1. Learning Outcome Heat Map
   2. Learning Outcome summary report at exam code
   3. Learning Outcome Table without heatmap.
2. Diksha Heatmap report
3. Responsive code development
4. Nifi process optimization
   1. Nifi main memory issues
   2. Nifi heap memory issues
   3. Nifi scheduler issue
5. UI screen for nifi process status
6. Upgradation from release 1.5 to 1.6
7. Release 1.6.1

**4.** **Description of the Product Features**

1\. PAT reports

[CQB-675](https://project-sunbird.atlassian.net/browse/CQB-675), [CQB-676](https://project-sunbird.atlassian.net/browse/CQB-676), [CQB-677](https://project-sunbird.atlassian.net/browse/CQB-677), [CQB-678](https://project-sunbird.atlassian.net/browse/CQB-678), [CQB-679](https://project-sunbird.atlassian.net/browse/CQB-679), [CQB-680](https://project-sunbird.atlassian.net/browse/CQB-680), [CQB-681](https://project-sunbird.atlassian.net/browse/CQB-681)

| Sl No. | Feature    | Description                                                     | Roles Impacted        |
| ------ | ---------- | --------------------------------------------------------------- | --------------------- |
| 1      | PAT report | - Heat Chart for the PAT learning outcome metrics visualization | Admin, Report viewers |

2\. Diksha TPD reports&#x20;

[CQB-686](https://project-sunbird.atlassian.net/browse/CQB-686) [CQB-687](https://project-sunbird.atlassian.net/browse/CQB-687), [CQB-688](https://project-sunbird.atlassian.net/browse/CQB-688), [CQB-689](https://project-sunbird.atlassian.net/browse/CQB-689)

| Sl No. | Feature    | Description                                                                                                                                                     | Roles Impacted        |
| ------ | ---------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------- |
| 1      | PAT report | Create a heatmap for Diksha TPD dataset which should represent the course progress and users enrolled over the last day, last 7 days, last 30 days and overall. | Admin, Report viewers |

3\. Responsive code development&#x20;

[CQB-694](https://project-sunbird.atlassian.net/browse/CQB-694)

| Sl No. | Feature                                                | Description                                                                                                               | Roles Impacted        |
| ------ | ------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------- | --------------------- |
| 1      | Responsive code development for the cQube landing page | The UI alignment for the cQube has been optimized and the display has been optimized for variations in screen resolution. | Admin, Report viewers |

4\. Nifi process optimization

[CQB-697](https://project-sunbird.atlassian.net/browse/CQB-697), [CQB-698](https://project-sunbird.atlassian.net/browse/CQB-698)

| Sl No. | Feature                                                         | Description                                                                                                                                                                                                                                                                        | Roles Impacted        |
| ------ | --------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------- |
| 1      | Nifi process optimization for main memory and heap memory issue | <p>Main memory issues resolved:</p><p>-          Nifi used to occupy high RAM space when multiple processor groups were running. This is optimized now.</p><p>Heap memory issues resolved:</p><p>-          OutOfMemoryError in nifi during data processing has been resolved.</p> | Admin, Report viewers |

5\. UI screen for nifi process status

[CQB-701](https://project-sunbird.atlassian.net/browse/CQB-701)

| Sl No. | Feature             | Description                                                                                | Roles Impacted        |
| ------ | ------------------- | ------------------------------------------------------------------------------------------ | --------------------- |
| 1      | Nifi process status | Nifi scheduler UI  screen has been modified and added a new column for nifi process status | Admin, Report viewers |

6\. Upgradation from release 1.5 to 1.6

[CQB-703,](https://project-sunbird.atlassian.net/browse/CQB-703) [CQB-704](https://project-sunbird.atlassian.net/browse/CQB-704)

| Sl No. | Feature                             | Description                                         | Roles Impacted        |
| ------ | ----------------------------------- | --------------------------------------------------- | --------------------- |
| 1      | Upgradation from release 1.5 to 1.6 | Ansible code development for PAT and Diksha reports | Admin, Report viewers |

7\. Release 1.6.1

[CQB-732,](https://project-sunbird.atlassian.net/browse/CQB-732) [CQB-750](https://project-sunbird.atlassian.net/browse/CQB-750), [CQB-751](https://project-sunbird.atlassian.net/browse/CQB-751), [CQB-753](https://project-sunbird.atlassian.net/browse/CQB-753), [CQB-754,](https://project-sunbird.atlassian.net/browse/CQB-754) [CQB-755](https://project-sunbird.atlassian.net/browse/CQB-755), [CQB-756,](https://project-sunbird.atlassian.net/browse/CQB-756) [CQB-757](https://project-sunbird.atlassian.net/browse/CQB-757), [CQB-758](https://project-sunbird.atlassian.net/browse/CQB-758)

| Sl No. | Feature                 | Description                                                                               | Roles Impacted        |
| ------ | ----------------------- | ----------------------------------------------------------------------------------------- | --------------------- |
| 1      | PAT and TPD heat map    | Heat map changes for PAT and TPD Reports                                                  | Admin, Report viewers |
| 2      | MAP changes             | Cropping of India map to Gujarat for all Map reports                                      | Admin, Report viewers |
| 3      | Nifi issue              | Negative values issue in Nifi processing                                                  | Admin, Report viewers |
| 4      | Admin statistics screen | Addition of PAT and TPD data sources in the admin statistics screen                       | Admin, Report viewers |
| 5      | PAT map (school level)  | 5,6,7 and 8 grades not displaying defect fix at the download file of PAT map school level | Admin, Report viewers |
| 6      | information icon        | Adding the i-icon for all landing page dashboard icons                                    | Admin, Report viewers |
| 7      | Alignment issues        | Other UI text alignments for all reports                                                  | Admin, Report viewers |
| 8      | API Certification       | Digital certificate add to the Emission and S3 output file download APIs                  |                       |

**5.** **Known Issues:**

This is a section that describes all the known issues/ bugs that are present in the cQube product and they have been reported as being a part of this release.

| Sl No | Issues                                                                                                                                                                                                                                                                                                                             |
| ----- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1     | PAT Heatchart - Select any district , block and cluster from select box and Select view by as question id  and mouse over on chart showing question id:undefined while selecting question id showing 2 records and change view by indicator it showing 6 records - [CQB 759](https://project-sunbird.atlassian.net/browse/CQB-759) |
