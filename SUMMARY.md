# Table of contents

## 📖 KNOW ABOUT CQUBE

* [What is cQube & what does it solve](README.md)
  * [Business case](know-about-cqube/architecture/business-case.md)
  * [cQube ed](know-about-cqube/architecture/cqube-ed.md)
  * [Design Principles](know-about-cqube/architecture/design-principles.md)
* [cQube adoptions](know-about-cqube/cqube-adoptions.md)
* [Discuss more about cQube](know-about-cqube/discuss-more-about-cqube.md)

## 👍 TRY CQUBE

* [cQube on Gitpod](try-cqube/architecture.md)

## 🌅 WHAT IS NEXT IN CQUBE

* [cQube Roadmap](what-is-next-in-cqube/architecture.md)

## 💻 TECHANICAL OVERVIEW

* [Architecture](techanical-overview/architecture.md)
* [Design Principles](techanical-overview/design-principles.md)
* [Key Components](techanical-overview/key-components.md)
* [Details of microservices](techanical-overview/details-of-microservices.md)

## 👩💻 Get started on cQube

* [Suggested Team Structure](get-started-on-cqube/getting-started.md)
* [Hardware Requirements](get-started-on-cqube/hardware-requirements.md)
* [Prerequisites Checklist](get-started-on-cqube/prerequisites-checklist.md)
* [Checking pre existing ports](get-started-on-cqube/checking-pre-existing-ports.md)
* [Instance Creation](get-started-on-cqube/instance-creation.md)
* [Copying SSL Certificate](get-started-on-cqube/copying-ssl-certificate.md)

## 🛃 USE CQUBE

* [How can I install cQube?](use-cqube/getting-started/README.md)
  * [High level understanding of deployment](use-cqube/getting-started/high-level-understanding-of-deployment.md)
  * [Oracle Installation](use-cqube/getting-started/oracle-installation.md)
  * [AWS Installation](use-cqube/getting-started/aws-installation.md)
  * [SDC Installation](use-cqube/getting-started/sdc-installation.md)
  * [Azure  Installation](use-cqube/getting-started/azure-installation.md)
* [How to prepare the data](use-cqube/getting-started-1/README.md)
  * [How to prepare dimension files](use-cqube/getting-started-1/how-to-prepare-dimension-files.md)
  * [How to Prepare Event Files](use-cqube/getting-started-1/how-to-prepare-event-files.md)
  * [Examples of dimension & event files](use-cqube/getting-started-1/examples-of-dimension-and-event-files.md)
  * [All cQube schemas used for VSK](use-cqube/getting-started-1/all-cqube-schemas-used-for-vsk.md)
* [Ingesting the data](use-cqube/ingesting-the-data/README.md)
  * [High-level understanding of ingestion](use-cqube/ingesting-the-data/high-level-understanding-of-ingestion.md)
  * [Adapter Details](use-cqube/ingesting-the-data/adapter-details.md)
  * [Postman Details](use-cqube/ingesting-the-data/postman-details.md)
  * [Steps to ingest schema](use-cqube/ingesting-the-data/steps-to-ingest-schema.md)
  * [Steps to Ingest data for a programs](use-cqube/ingesting-the-data/steps-to-ingest-data-for-a-programs.md)
  * [National Programs API to upload starter Pack Data files](use-cqube/ingesting-the-data/api-details.md)
  * [Error during ingestion](use-cqube/ingesting-the-data/error-during-ingestion.md)
* [Processing of data](use-cqube/processing-of-data/README.md)
  * [Data Processing using CLI command](use-cqube/processing-of-data/data-processing-using-cli-command.md)
  * [API Details for Nifi-Rest](use-cqube/processing-of-data/api-details-for-nifi-rest.md)
  * [Nifi data](use-cqube/processing-of-data/nifi-data.md)
* [Visualizing the data](use-cqube/visualizing-the-data/README.md)
  * [High level understanding of how visualizations work in cQube](use-cqube/visualizing-the-data/high-level-understanding-of-how-visualizations-work-in-cqube.md)
  * [Programs and reports out-of-the-box](use-cqube/visualizing-the-data/programs-and-reports-out-of-the-box.md)
* [Additional Features](use-cqube/additional-features/README.md)
  * [Public/Private dashboards](use-cqube/additional-features/public-private-dashboards.md)
  * [Role based access control](use-cqube/additional-features/role-based-access-control.md)
  * [Saving geographical preferences](use-cqube/additional-features/saving-geographical-preferences.md)
  * [Admin Panel](use-cqube/additional-features/admin-panel/README.md)
    * [Data Debugger](use-cqube/additional-features/admin-panel/data-debugger.md)
    * [Schema creator](use-cqube/additional-features/admin-panel/schema-creator.md)
    * [System Monitoring](use-cqube/additional-features/admin-panel/system-monitoring.md)
* [Adding Users](use-cqube/adding-users/README.md)
  * [Adding  an individual user](use-cqube/adding-users/adding-an-individual-user.md)
  * [Adding bulk users](use-cqube/adding-users/adding-bulk-users.md)

## 🖥 MONITOR cQUBE

* [Infra health monitoring](monitor-cqube/getting-started.md)
* [Usage monitoring](monitor-cqube/usage-monitoring.md)

## 🔎 QA testing

* [Testing approaches & activities](qa-testing/ui-customisations.md)
* [Manual & Automated testing](qa-testing/manual-and-automated-testing.md)
* [Functional Testing](qa-testing/functional-testing/README.md)
  * [Smoke Testing](qa-testing/functional-testing/smoke-testing.md)
  * [Functional tests](qa-testing/functional-testing/functional-tests.md)
  * [Regression Testing](qa-testing/functional-testing/regression-testing.md)
  * [System Testing](qa-testing/functional-testing/system-testing.md)
* [Non Functional Testing](qa-testing/non-functional-testing/README.md)
  * [Performance Testing](qa-testing/non-functional-testing/performance-testing/README.md)
    * [Load Testing](qa-testing/non-functional-testing/performance-testing/load-testing.md)
    * [Volume Testing](qa-testing/non-functional-testing/performance-testing/volume-testing.md)
    * [Performance testing results](qa-testing/non-functional-testing/performance-testing/performance-testing-results.md)
* [Test for One-Step Installation](qa-testing/test-for-one-step-installation.md)
* [Test for Ingestion](qa-testing/test-for-ingestion.md)
* [Test for nifi processing](qa-testing/test-for-nifi-processing.md)
* [Test for UI Application](qa-testing/test-for-ui-application.md)
* [Test for KPIs](qa-testing/test-for-kpis.md)

## ☀ DEPLOYMENT PROCESS

* [State List](deployment-process/state-list.md)
* [AWS Deployment](deployment-process/aws-deployment.md)
* [SDC Deployment](deployment-process/sdc-deployment.md)
* [Processor Group Name](deployment-process/processor-group-name.md)
* [Adapter Details During the Processing](deployment-process/adapter-details-during-the-processing.md)

## ☀  ENHANCE/CUSTOMIZE CQUBE

* [Available customizations](enhance-customize-cqube/manual-and-automated-testing/README.md)
  * [Changing Dashboard Logos and Headers](enhance-customize-cqube/manual-and-automated-testing/changing-dashboard-logos-and-headers.md)
  * [Changing Program Name, Icon and Side Menu Sequence](enhance-customize-cqube/manual-and-automated-testing/changing-program-name-icon-and-side-menu-sequence.md)
  * [Adding a new KPI](enhance-customize-cqube/manual-and-automated-testing/adding-a-new-kpi.md)
  * [Adding a Map KPI into dashboard ms](enhance-customize-cqube/manual-and-automated-testing/adding-a-map-kpi-into-dashboard-ms.md)
  * [Table Drill Down Customization](enhance-customize-cqube/manual-and-automated-testing/table-drill-down-customization.md)
  * [Adding a Scatter Plot KPI into dashboard ms](enhance-customize-cqube/manual-and-automated-testing/adding-a-scatter-plot-kpi-into-dashboard-ms.md)
  * [Configure default date range across app/specific report](enhance-customize-cqube/manual-and-automated-testing/configure-default-date-range-across-app-specific-report.md)
* [How to add a New Indicator](enhance-customize-cqube/functional-testing.md)
* [How to add a new report in an existing program](enhance-customize-cqube/test-for-one-step-installation.md)
* [How to add a  new program (end to end)](enhance-customize-cqube/test-for-ingestion.md)

## 🈴 UPGRADING TO LATEST VERSION

* [How can I upgrade cQube to the latest release](upgrading-to-latest-version/ui-customisations.md)

## 🆘 Common issues and their solutions

* [Deployment & ingestion related issues & their solutions](common-issues-and-their-solutions/ui-customisations.md)

## ⏱ Standard Operating Procedure

* [Reporting a Bug](standard-operating-procedure/reporting-a-bug.md)
* [Protocol for issue reporting & resolution](standard-operating-procedure/requesting-for-support.md)
* [Suggesting Enhancements](standard-operating-procedure/suggesting-enhancements.md)
* [Raising a PR](standard-operating-procedure/raising-a-pr.md)

## ❓ Frequently Asked Questions

* [Running List](frequently-asked-questions/reporting-a-bug.md)

## 🧑🏫 🧑🏫 Recording of trainings

* [Link to the training videos](recording-of-trainings/reporting-a-bug.md)

## 🧠 Key Terms & Concepts

* [Definitions](key-terms-and-concepts/reporting-a-bug.md)

## 🚀 cQube Release Notes <a href="#release-notes" id="release-notes"></a>

* [cQube - Release V 5.0.5](release-notes/cqube-release-v-5.0.5.md)
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
