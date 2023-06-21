# cQube - Release V 5.0

**Document Release Version**

<table><thead><tr><th width="527.3333333333333">Project</th><th>Release Date</th><th>Release Version</th></tr></thead><tbody><tr><td>cQube</td><td>27 Mar 2023</td><td>V 5.0</td></tr></tbody></table>

## Overview

As part of cQube V 5.0, a cQube adopter can install V 5.0 or upgrade from V 4.1 Beta to V 5.0 seamlessly, ingest spec-compliant data for 9 out-of-the-box programs & leverage RBAC-enabled visualisation layer of cQube for all programs. cQube adopter can also add a new program or indicator easily and connect cQube datasets to external visualisation tools (like Metabase, Tableau etc.)

## Release Highlights

1. **📊 Pre-Packaged Programs:** 20+ out-of-the-box education programs, out of which 9 are live as part of this version with an additional ability for the cQube adopter to add new programs within 2 days
2. **👥 Decentralised Observability:** Visualisations for all out-of-the-box programs tailored to user role and jurisdictions. For example, a state officer will look at state and district-level data for all districts in the state. A district officer selects their district and looks at data for their districts and all the blocks in the district
3. **🧑‍💻 Quick and Smooth Set Up:** Seamless installation of cQube V 5.0 and upgradation from V 4.1 - beta to V 5.0 in less than 30 minutes
4. **🔁 Direct Linkage for Data Updates:** Automatic updation of daily-level data by direct linkage of the state data sources with cQube
5. **📈 Usage Tracking Mechanism:** Track usage of dashboards for each program via telemetry

## Release Features

1. A deployer can install V 5.0 or upgrade from V 4.1 - Beta (VSK Starter Pack) to V 5.0 seamlessly within 30 minutes - [Installation Details](../installation-and-upgradation/step-wise-installation-process.md) | [Upgradation Details](../installation-and-upgradation/step-wise-upgradation-process.md)
2. A deployer is able to ingest state data for 9 out-of-the-box programs in cQube schema via APIs through adapters at a set frequency - [Available Programs](../data-visualisation/programs-reports-and-indicators.md) | [cQube Schema](broken-reference) | [Adapter Creation](../data-ingestion-and-processing/step-wise-adapter-creation-process.md) | [Ingestion Details](broken-reference)
3. A deployer can monitor ingestion by viewing the number of rows ingested and rectifying any errors - [Monitoring Ingestion](broken-reference) | [Rectifying Errors](broken-reference)
4. A deployer is able to schedule the processing of ingested data within cQube - [Installation Details](../installation-and-upgradation/step-wise-installation-process.md)
5. A deployer can add a new program / report / indicator in cQube by configuring ingestion, processing and visualisation
6. A deployer / admin can connect the cQube datasets to any external visualisation tool (eg: Metabase, Tableau etc.)
7. A deployer can modify the UI of the cQube dashboards through configurations - [UI Customisations](../data-visualisation/ui-customisations.md)
8. A user can select the role (State Officer, District Officer, Block Officer, Cluster Officer, School Principal, Class Teacher) & jurisdiction (District, Block, Cluster, School, Class) for which they want to view data / charts on the cQube dashboard for all out-of-the-box programs
9. A user can apply relevant filters to data available for all programs
10. A user can see a summary dashboard with important data points from all programs
11. A user can see when the data was last updated for all programs on the cQube dashboard
12. A user can download data for a specific chart / report into a CSV
13. An admin can monitor and track usage of dashboards regularly (Unique users, Page-wise total views, Day & week-wise views etc.)

## Backward Compatibility

cQube users on VSK Starter Pack (V 4.1 Beta) with 6 out-of-the-box programs like NAS, UDISE, PGI, DIKSHA, NISHTHA and PM-POSHAN can upgrade to V 5.0 within 30 minutes using [these](../installation-and-upgradation/step-wise-upgradation-process.md) steps. The hardware and software requirements for [V 5.0](../installation-and-upgradation/hardware-requirements.md) are same (actually - lesser) as [V 4.1 Beta](../cqube-v-4.1-beta/network-architecture-diagram/hardware-requirements.md).

For the users who upgrade to cQube V 5.0, their existing data for the 6 programs in the VSK Starter Pack will automatically become compliant to V 5.0 and they will be able to see the same programs with state data in V 5.0.

The existing users of the VSK Starter Pack can continue updating the data for the 6 national programs (NAS, UDISE, PGI, DIKSHA, NISHTHA and PM-POSHAN) in the same ZIP format of the file using the [new API](broken-reference) in the same manner.&#x20;

In case the existing users of VSK Starter Pack also wish to see the state programs that come out-of-the-box in cQube V5.0 (Student Attendance, Teacher Attendance & Review Meetings), they will need to ingest the state data in the manner explained [here](broken-reference).

cQube users on any other version, who wish to upgrade to cQube V 5.0, please reach out to the cQube Product Team [here](https://github.com/Sunbird-cQube/community/discussions/categories/q-a).

## Deprecations from previous release (V 4.1 - beta)

Some features have been deprecated from the previous release (V 4.1 - beta) but will be available in the future versions of cQube as mentioned here:

1. **Login Page:** A login page is not present in cQube V 5.0. The aggregated data (there is no PII data in cQube) can be accessed by all officers in the state according to the role that they select. The login functionality will be available in V 5.0.1, planned to be released by mid-April'23. The ticket for this functionality can be tracked [here](https://project-sunbird.atlassian.net/browse/CQ-428?atlOrigin=eyJpIjoiMzg0ODM3ZGY0ZjAxNGM4N2I3MDU5MjE0ZWJkZmI1ODUiLCJwIjoiaiJ9).
2. **Admin Console:** A UI-based admin console will not be available in cQube V 5.0 but most of the functionalities of the admin console have been enabled via APIs as explained below:
   1. Monitoring of ingestion and processing: The deployer can see the number of ingested rows in cQube V 5.0 along with the errors in the ingested file using the file status API as explained [here](broken-reference).
   2. Managing retention and deletion of ingested data: This feature will be available in V 5.0.2, planned to be released at the end of April'23.
   3. Scheduling the processing of ingested data: This can be done using the schedule API in V 5.0 as explained [here](broken-reference).

## Available Documentations for V 5.0

1. [Getting Started](../installation-and-upgradation/getting-started.md)
2. [Step-wise Installation Process](../installation-and-upgradation/step-wise-installation-process.md)
3. [cQube Schemas](broken-reference)
4. [Step-wise Adapter Creation Process](../data-ingestion-and-processing/step-wise-adapter-creation-process.md)
5. [Step-wise Ingestion Process](broken-reference)
6. [Available programs, reports and indicators](../data-visualisation/programs-reports-and-indicators.md)
7. [UI Customisations](../data-visualisation/ui-customisations.md)

## Known Issues

_To be published soon!_

## Scale Testing Results

_To be published soon!_

## Upcoming Release Features

The list of features for the upcoming releases can be accessed from this [link](https://docs.google.com/spreadsheets/d/1e8b\_kLCfD0Oce9Jek4nrpBFQRk-IJOKgYy5GOnFs8Ho/edit#gid=1589485385). Any comments for suggestions are welcome in the attached document.
