# Usage monitoring

**Telemetry Process**

Telemetry is a database which provides the website traffic information to the users.  This tool provides datapoints like number of visitors, their access style (devices) and the report type they have accessed, etc.&#x20;

1. KPIs/Metrics captured:&#x20;

&#x20;            a. Most Visited Landing Pages

&#x20;            b. Users Count

&#x20;            c. Average time spent on each page

&#x20;            d. Unique Users across Browser & Device Types

&#x20;            e. Roll-Up of users using (Daily, Weekly)

&#x20;            f.  Click, Select, Download

2. Define Events, Dimensions & Schema

eventName : telemetry-event.data

<table data-header-hidden><thead><tr><th></th><th width="165"></th><th></th><th></th><th></th><th></th><th></th><th></th><th></th><th></th><th></th><th></th></tr></thead><tbody><tr><td>date</td><td>timestamp</td><td>userId</td><td>pageName</td><td>pageEvent</td><td>pageEventName</td><td>deviceType</td><td>userLocation</td><td>browserType</td><td>timeSpent</td><td>timeIn</td><td>timeOut</td></tr><tr><td>24/04/23</td><td>13:00:11</td><td>cf797e0a-b857-47f1-b0d7-10bd83231421</td><td>teacher-attendance</td><td>click</td><td>download</td><td>web</td><td>Bengaluru</td><td>chrome</td><td><br></td><td><br></td><td><br></td></tr><tr><td>24/04/23</td><td>13:00:11</td><td>cf797e0a-b857-47f1-b0d7-10bd83231421</td><td>teacher-attendance</td><td>onload</td><td>pageLoad</td><td>mobile</td><td>Bengaluru</td><td>firefox</td><td>3213</td><td>13:10:02</td><td>13:13:02</td></tr><tr><td>24/04/23</td><td>13:00:11</td><td>cf797e0a-b857-47f1-b0d7-10bd83231421</td><td>pgi</td><td>click</td><td>apply</td><td>web</td><td>Bengaluru</td><td>chrome</td><td><br></td><td><br></td><td><br></td></tr><tr><td>24/04/23</td><td>13:00:11</td><td>cf797e0a-b857-47f1-b0d7-10bd83231421</td><td>teacher-attendance</td><td>click</td><td>cancel</td><td>mobile</td><td>Bengaluru</td><td>chrome</td><td><br></td><td><br></td><td><br></td></tr><tr><td>24/04/23</td><td>13:00:11</td><td>cf797e0a-b857-47f1-b0d7-10bd83231421</td><td>login</td><td>login</td><td><br></td><td><br></td><td><br></td><td><br></td><td><br></td><td><br></td><td><br></td></tr></tbody></table>

<figure><img src="../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

3\. Workflow

&#x20;                The diagram explains about the flow of the telemetry works.&#x20;

<figure><img src="../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

4. Visualize the reports.
5. Steps done for enabling telemetry

&#x20;           a. Create a python script for splitting up multi metrics into single metric (https://github.com/Sunbird-cQube/generator-ms/blob/release-v5.0.5/adapter/telemetry.py).

&#x20;            b. Add the telemetry details in config.json file (https://github.com/Sunbird-cQube/processing-ms/blob/release-v5.0.5/impl/c-qube/ingest/VSK/config.json).

&#x20;            c. Create nifi processor group to schedule for moving data and processing

&#x20;            d. Add new UI report

&#x20;            e. Add the logics in UI to capture the events

&#x20;            f. Create the grammars&#x20;
