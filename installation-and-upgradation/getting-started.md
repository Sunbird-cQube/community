---
description: 'Shows you a list of things to help you get started with cQube V 5.0:'
---

# Getting Started - Suggested Team Structure

cQube v5.0, the latest version of cQube, enables monitoring of 9 out-of-the-box state and national education programs for performance improvement. All of these programs will be tailored to the user role and jurisdiction. Any new program can also be added by the state for monitoring purposes.

To get started with cQube, the following team composition is suggested:

| Type              | Language / Skills                     | Experience | Full-time people |
| ----------------- | ------------------------------------- | ---------- | ---------------- |
| Backend Developer | TypeScript, NestJS                    | 3+ years   | 1                |
| DevOps            | Docker, Ansible                       | 3+ years   | 1                |
| QA                | UAT                                   | 3+ years   | 1                |
| Tech Lead         | All of the above, & management skills | 5+ years   | 1                |

To enable any customizations/add new programs, following members are suggested in addition to the above:

| Type               | Language / Skills          | Experience | Full-time people |
| ------------------ | -------------------------- | ---------- | ---------------- |
| Backend Developer  | Nest.js, Python, NiFi, SQL | 4+ years   | 1                |
| Frontend Developer | Angular                    | 3+ years   | 1                |

\
The detailed skill sets required for each phase of the setting up process are mentioned below:

<table data-header-hidden><thead><tr><th width="191"></th><th></th></tr></thead><tbody><tr><td>Configure</td><td><ul><li>Knowledge of defining the grammars (dimensions, event) and verifying CSVs (data files for dimensions and events)</li><li>Basic knowledge of Pandas + Python to clean data if needed.</li></ul></td></tr><tr><td>Deploy</td><td><ul><li>Shell scripting, AWS, Ansible, Docker (build, deploy, update containers; Verify from logs connections)</li><li>Nginx, Networking, Ubuntu.</li></ul></td></tr><tr><td>Monitor</td><td><ul><li>Knowledge of defining the grammars (dimensions, event) and verifying CSVs (data files for dimensions and events) and KPI and their definitions</li><li>Basic of Database to verify SQL queries or construct new ones if needed</li><li>Ability to use GitHub to raise tickets, issues.</li></ul></td></tr><tr><td>Maintain</td><td><ul><li>Ansible, Docker (build, deploy, update containers; Verify from logs connections), Nginx, Networking, Ubuntu</li></ul></td></tr><tr><td>Enhance &#x26; contribute (Frontend)</td><td><ul><li>Angular 14</li><li>Good understanding of MVC</li><li>Understanding of javascript and typescript</li><li>Debugging skills; Basics of Dockerfile</li></ul></td></tr><tr><td>Enhance &#x26; contribute (Backend)</td><td><ul><li>Basic knowledge of Database to verify SQL queries or construct efficient new ones if needed</li><li>Knowledge of how datasets are created in cQube</li><li>NestJS, Typescript, Postgres</li></ul></td></tr><tr><td>Enhance &#x26; contribute (Ingestion)</td><td><ul><li>Should only be done by the core team</li></ul></td></tr><tr><td>Enhance &#x26; contribute (DevOps)</td><td><ul><li>Ansible, Docker, Nginx, Networking, Ubuntu</li><li>Worked previously on an IaC codebase (<a href="https://www.redhat.com/en/topics/automation/what-is-infrastructure-as-code-iac">https://www.redhat.com/en/topics/automation/what-is-infrastructure-as-code-iac</a>)</li></ul></td></tr></tbody></table>

## Supported Servers & Clouds

1. AWS - The steps to deploy cQube v5.0 on AWS have been mentioned [here](step-wise-installation-process.md)
2. On premise (State Data Centre, Local) - The steps to deploy cQube v5.0 on 'On premise' (State Data Centre, Local) have been mentioned [here](broken-reference)
3. OCI - The steps to deploy are mentioned [here](broken-reference)
