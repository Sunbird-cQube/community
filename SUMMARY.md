# Table of contents

* [Product Overview](README.md)

## 👩💻 👩💻 Installation & Upgradation

* [Getting Started - Suggested Team Structure](installation-and-upgradation/getting-started.md)
* [Hardware Requirements](installation-and-upgradation/hardware-requirements.md)
* [Checking pre existing ports](installation-and-upgradation/checking-pre-existing-ports.md)
* [Steps to setup instance: Server-wise](installation-and-upgradation/step-wise-installation-process.md)
  * [Oracle Cloud Instance Setup](installation-and-upgradation/step-wise-installation-process/oracle-cloud-instance-setup.md)
  * [AWS Instance Setup](installation-and-upgradation/step-wise-installation-process/aws-instance-setup.md)
  * [SDC Instance setup](installation-and-upgradation/step-wise-installation-process/sdc-instance-setup.md)
* [Next Steps for installation](installation-and-upgradation/next-common-steps/README.md)
  * [Common steps](installation-and-upgradation/next-common-steps/common-steps.md)
  * [AWS Steps](installation-and-upgradation/next-common-steps/aws-steps.md)
  * [SDC Steps](installation-and-upgradation/next-common-steps/sdc-steps.md)
* [End to End Installation on Local Setup](installation-and-upgradation/end-to-end-installation-on-local.md)
* [Step-wise Upgradation Process](installation-and-upgradation/step-wise-upgradation-process.md)
* [Microservices details](installation-and-upgradation/microservices-details.md)

## 🔐 User Authentication

* [Configuring Keycloak](user-authentication/configuring-keycloak.md)
* [Adding Users](user-authentication/adding-users.md)

## 💻 Technical Overview

* [Architecture](technical-overview/architecture.md)
* [Design Principles](technical-overview/design-principles.md)
* [Key Components](technical-overview/key-components.md)

## 📄 Steps to Prepare Data

* [Important Note](steps-to-prepare-data/important-note.md)
* [Define Dimension Schema](steps-to-prepare-data/define-dimension-schema.md)
* [Define Events / Facts Schema](steps-to-prepare-data/events-facts.md)
* [Example of cQube Dimension & Event Schema](steps-to-prepare-data/example-of-cqube-dimension-and-event-schema/README.md)
  * [Link to all cQube schemas](steps-to-prepare-data/example-of-cqube-dimension-and-event-schema/link-to-all-cqube-schemas.md)

## 🔃 Data Ingestion & Processing

* [Adapter Details](data-ingestion-and-processing/step-wise-adapter-creation-process/README.md)
  * [Architecture](data-ingestion-and-processing/step-wise-adapter-creation-process/architecture.md)
  * [Technology Used](data-ingestion-and-processing/step-wise-adapter-creation-process/technology-used.md)
  * [Working of an Adapter](data-ingestion-and-processing/step-wise-adapter-creation-process/working-of-an-adapter.md)
* [High Level Understanding of Data Ingestion](data-ingestion-and-processing/high-level-understanding-of-data-ingestion.md)
* [Setting up Postman](data-ingestion-and-processing/setting-up-postman/README.md)
  * [Postman collection files](data-ingestion-and-processing/setting-up-postman/postman-collection-files.md)
* [Steps to add schemas for a program & for dimensions](data-ingestion-and-processing/steps-to-add-schemas-for-a-program-and-for-dimensions.md)
* [Step-wise Ingestion Process](data-ingestion-and-processing/step-wise-ingestion-process/README.md)
  * [Generate JWT token API](data-ingestion-and-processing/step-wise-ingestion-process/generate-jwt-token-api.md)
  * [Upload the csv data file for new programs using ingestion API](data-ingestion-and-processing/step-wise-ingestion-process/upload-the-csv-data-file-for-new-programs-using-ingestion-api.md)
* [Example: National Programs API](data-ingestion-and-processing/example-national-programs-api/README.md)
  * [GET File status API](data-ingestion-and-processing/example-national-programs-api/get-file-status-api.md)
  * [Schedule API](data-ingestion-and-processing/example-national-programs-api/schedule-api.md)
  * [Error Monitoring](data-ingestion-and-processing/example-national-programs-api/error-monitoring.md)
  * [Data Ingestion using CLI Command](data-ingestion-and-processing/example-national-programs-api/data-ingestion-using-cli-command/README.md)
    * [Ingestion of Dimensions](data-ingestion-and-processing/example-national-programs-api/data-ingestion-using-cli-command/ingestion-of-dimensions.md)
    * [Ingestion of Program Data](data-ingestion-and-processing/example-national-programs-api/data-ingestion-using-cli-command/ingestion-of-program-data.md)
    * [Delete the data in the database](data-ingestion-and-processing/example-national-programs-api/data-ingestion-using-cli-command/delete-the-data-in-the-database.md)
* [Common Error During Data Ingestion](data-ingestion-and-processing/common-error-during-data-ingestion.md)
* [NiFi](data-ingestion-and-processing/nifi.md)
* [Error Monitoring](data-ingestion-and-processing/error-monitoring.md)
* [Step-wise Ingestion Process \[State Programs\]](data-ingestion-and-processing/step-wise-ingestion-process-state-programs/README.md)
  * [Error Monitoring](data-ingestion-and-processing/step-wise-ingestion-process-state-programs/error-monitoring.md)

## 📊 Dashboard, Visualizations and Reports

* [High level view of how visualizations work](dashboard-visualizations-and-reports/high-level-view-of-how-visualizations-work.md)
* [Programs, Reports & Indicators](dashboard-visualizations-and-reports/programs-reports-and-indicators/README.md)
  * [Teacher Attendance](dashboard-visualizations-and-reports/programs-reports-and-indicators/teacher-attendance.md)
  * [Student Attendance](dashboard-visualizations-and-reports/programs-reports-and-indicators/student-attendance.md)
  * [PM POSHAN](dashboard-visualizations-and-reports/programs-reports-and-indicators/pm-poshan.md)
  * [PGI](dashboard-visualizations-and-reports/programs-reports-and-indicators/pgi.md)
  * [UDISE+](dashboard-visualizations-and-reports/programs-reports-and-indicators/udise+.md)
  * [NAS](dashboard-visualizations-and-reports/programs-reports-and-indicators/nas.md)
  * [DIKSHA](dashboard-visualizations-and-reports/programs-reports-and-indicators/diksha.md)
  * [Review Meetings](dashboard-visualizations-and-reports/programs-reports-and-indicators/review-meetings.md)
  * [NISHTHA](dashboard-visualizations-and-reports/programs-reports-and-indicators/nishtha.md)

## ⚙ UI Configurations

* [UI Customisations](ui-configurations/ui-customisations/README.md)
  * [Changing Dashboard Logos and Headers](ui-configurations/ui-customisations/changing-dashboard-logos-and-headers.md)
  * [Changing Program Name, Icon and Side Menu Sequence](ui-configurations/ui-customisations/changing-program-name-icon-and-side-menu-sequence.md)
* [Connecting cQube Datasets to External Visualisation Tools](ui-configurations/connecting-cqube-datasets-to-external-visualisation-tools.md)
* [Adding a New Program](ui-configurations/adding-a-new-program.md)
* [Adding a New Report](ui-configurations/adding-a-new-report.md)
* [Adding a New Indicator](ui-configurations/adding-a-new-indicator.md)
* [Adding a Scatter Plot KPI into dashboard ms](ui-configurations/additional-customizations/README.md)
  * [Adding a new KPI](ui-configurations/additional-customizations/adding-a-new-kpi.md)
  * [Table DrillDown Customization](ui-configurations/additional-customizations/table-drilldown-customization.md)
  * [Adding a Map KPI into dashboard ms](ui-configurations/additional-customizations/adding-a-map-kpi-into-dashboard-ms.md)
  * [Configure default date range across app/specific report](ui-configurations/additional-customizations/configure-default-date-range-across-app-specific-report.md)
  * [Page 1](ui-configurations/additional-customizations/page-1.md)

## 🔎 QA testing

* [Testing approaches & activities](qa-testing/ui-customisations.md)
* [Manual & Automated testing](qa-testing/manual-and-automated-testing.md)
* [Functional Testing](qa-testing/functional-testing/README.md)
  * [Smoke Testing](qa-testing/functional-testing/smoke-testing.md)
  * [Functional tests](qa-testing/functional-testing/functional-tests.md)
  * [Regression Testing](qa-testing/functional-testing/regression-testing.md)
  * [System Testing](qa-testing/functional-testing/system-testing.md)
* [Test for One-Step Installation](qa-testing/test-for-one-step-installation.md)
* [Test for Ingestion](qa-testing/test-for-ingestion.md)
* [Test for nifi processing](qa-testing/test-for-nifi-processing.md)
* [Test for UI Application](qa-testing/test-for-ui-application.md)
* [Test for KPIs](qa-testing/test-for-kpis.md)

## 🆘 Common issues and their solutions

* [Deployment & ingestion related issues & their solutions](common-issues-and-their-solutions/ui-customisations.md)

## ⏱ Standard Operating Procedure

* [Reporting a Bug](standard-operating-procedure/reporting-a-bug.md)
* [Requesting for Support](standard-operating-procedure/requesting-for-support.md)
* [Suggesting Enhancements](standard-operating-procedure/suggesting-enhancements.md)

## ❓ Frequently Asked Questions

* [Running List](frequently-asked-questions/reporting-a-bug.md)

## 🧑🏫 Recording of trainings

* [Link to the training videos](recording-of-trainings/reporting-a-bug.md)

## 🧠 Key Terms & Concepts

* [Definitions](key-terms-and-concepts/reporting-a-bug.md)

## 🚀 cQube Release Notes <a href="#release-notes" id="release-notes"></a>

* [cQube - Release V 5.0.3](release-notes/cqube-release-v-5.0.3.md)
* [cQube - Release V 5.0.2](release-notes/cqube-release-v-5.0.2.md)
* [cQube - Release V 5.0.1](release-notes/cqube-release-v-5.0.1.md)
* [cQube - Release V 5.0](release-notes/cqube-release-v-5.0.md)
* [cQube - Release V 4.1-beta](release-notes/cqube-release-notes-v4.1-beta.md)
* [cQube - Release V 4.0-beta](release-notes/cqube-release-notes-v4.0-beta.md)
* [cQube - Release V 4.0-alpha](release-notes/cqube-release-notes-v4.0-alpha.md)
* [cQube - Release V 3.7](release-notes/cqube-release-notes-v-3.7.md)
* [cQube - Release V 3.6](release-notes/cqube-release-notes-v-3.6.md)
* [cQube - Release V 3.5](release-notes/cqube-release-notes-v-3.5.md)
* [cQube - Release V 3.4](release-notes/cqube-release-notes-v-3.4.md)
* [cQube - Release V 3.3](release-notes/cqube-release-v-3.3.md)
* [cQube - Release V 3.2](release-notes/cqube-release-notes-v-3.2.md)
* [cQube - Release V 3.1](release-notes/cqube-release-v-3.1.md)
* [cQube - Release V 3](release-notes/cqube-release-v-3.md)
* [cQube - Release V 2](release-notes/cqube-release-v-2.md)
* [cQube - Release V 1.13 and V 1.13.1](release-notes/cqube-release-v-1.13-and-v-1.13.1.md)
* [cQube - Release V 1.12 and V 1.12.1](release-notes/cqube-release-v-1.12-and-v-1.12.1.md)
* [cQube - Release V 1.11](release-notes/cqube-release-v-1.11.md)
* [cQube - Release V 10 and V 10.1](release-notes/cqube-release-v-10-and-v-10.1.md)
* [cQube - Release V 1.9](release-notes/cqube-release-v-1.9.md)
* [cQube - Release V 1.8 and V 1.8.1](release-notes/cqube-release-v-1.8-and-v-1.8.1.md)
* [cQube - Release Notes V 1.7](release-notes/cqube-release-notes-v-1.7.md)
* [cQube - Release Notes V 1.6 and V 1.6.1](release-notes/cqube-release-notes-v-1.6.md)
* [cQube - Release Notes V 1.5](release-notes/cqube-release-notes-v-1.5.md)
* [cQube - Release Notes V 1.4](release-notes/cqube-release-notes-v-1.4.md)
* [cQube - Release Notes V 1.3](release-notes/cqube-release-v1.3.md)
* [cQube - Release Notes V 1.2 and V 1.2.1](release-notes/cqube-release-notes-v1.2-and-v1.2.1.md)
* [cQube - Release Notes V 1.1](release-notes/cqube-release-notes-v1.1.md)
* [cQube - Release Notes V 1.0](release-notes/cqubeversion-1.0.md)

## 📂 cQube V 4.1 - Beta

* [Sunbird cQube Overview](cqube-v-4.1-beta/readme.md)
* [cQube Product Description](cqube-v-4.1-beta/cqube-features.md)
* [Listen to Experts (Youtube)](https://www.youtube.com/watch?v=kbeFmTsWlAI)
* [Software Requirements](cqube-v-4.1-beta/software-requirements.md)
* [Acronyms](cqube-v-4.1-beta/acronyms.md)
* [cQube Software Architecture](cqube-v-4.1-beta/cqube-software-architecture.md)
* [AWS - Network Architecture](cqube-v-4.1-beta/network-architecture-diagram/README.md)
  * [Hardware requirements](cqube-v-4.1-beta/network-architecture-diagram/hardware-requirements.md)
  * [Data Storage Locations](cqube-v-4.1-beta/network-architecture-diagram/data-storage-locations.md)
* [Security Implementations](cqube-v-4.1-beta/security-requirements.md)
* [Prerequisites for Installation process](cqube-v-4.1-beta/prerequisites-for-installation-process.md)
* [New Use-Case Creation](cqube-v-4.1-beta/use-case.md)
* [cQube Setup & configuration](cqube-v-4.1-beta/cqube-installation.md)
* [Base Installation steps](cqube-v-4.1-beta/base-installation-steps.md)
* [Base Upgradation steps](cqube-v-4.1-beta/base-upgradation-steps.md)
* [Workflow Installation steps](cqube-v-4.1-beta/workflow-installation-steps.md)
* [Workflow Upgradation steps](cqube-v-4.1-beta/workflow-upgradation-steps.md)
* [Laptop/Desktop Installation](cqube-v-4.1-beta/laptop-desktop-demo-installation/README.md)
  * [Base Installation](cqube-v-4.1-beta/laptop-desktop-demo-installation/base\_installation.md)
  * [Workflow Installation](cqube-v-4.1-beta/laptop-desktop-demo-installation/workflow\_installation.md)
  * [Mock Data Processing](cqube-v-4.1-beta/laptop-desktop-demo-installation/mock-data-processing.md)
* [Ad-hoc analysis](cqube-v-4.1-beta/ad-hoc-analyst.md)
* [Workflow process](cqube-v-4.1-beta/workflow-process.md)
* [Emission Process](cqube-v-4.1-beta/emission-process-1.md)
* [cQube ER Diagrams](cqube-v-4.1-beta/cqube-er-diagrams.md)
* [Data Validation after Ingestion](cqube-v-4.1-beta/data-validation-after-ingestion.md)
* [User Authentication Process](cqube-v-4.1-beta/authentication\_process.md)
* [Admin Login Process](cqube-v-4.1-beta/admin-login-process.md)
* [Admin Features](cqube-v-4.1-beta/admin-features.md)
* [cQube Datasource Configuration](cqube-v-4.1-beta/datasource\_configuration.md)
* [cQube data replay process](cqube-v-4.1-beta/cqube-data-replay-process.md)
* [S3 Partitioning](cqube-v-4.1-beta/design-principles.md)
* [Reports](cqube-v-4.1-beta/reports.md)
* [Troubleshooting Issues](cqube-v-4.1-beta/troubleshooting-issues/README.md)
  * [Data Processing-NIFI Issues](cqube-v-4.1-beta/troubleshooting-issues/data-processing-nifi-issues.md)
  * [Data Processing-PostgreSQL Issues](cqube-v-4.1-beta/troubleshooting-issues/data-processing-postgresql-issues.md)
  * [Data Emission Issues](cqube-v-4.1-beta/troubleshooting-issues/data-emission-issues.md)
  * [Angular & Node Issues](cqube-v-4.1-beta/troubleshooting-issues/angular-and-node-issues.md)
* [FAQs](cqube-v-4.1-beta/faqs.md)
* [Discuss](https://github.com/Sunbird-cQube/community/discussions)
* [Report](https://github.com/Sunbird-cQube/community/issues)
* [Source Code](https://github.com/Sunbird-cQube)
