---
description: Explains the process to add a new program into cQube Ed
---

# Adding a New Program

### Create event and dimension Grammar files:

Design the event and dimension grammar files for your program. This grammar defines the structure and relationships between different data elements, such as event attributes and dimensions.

* Event grammar: The event grammar defines the structure of the events to be ingested into the system. It includes information such as the event name, its attributes (e.g. event timestamp, user ID, etc.), and data types.
* Dimension grammar: The dimension grammar defines the dimensions, or attributes, that will be used to group and filter events. It includes information such as the dimension name, its attributes (e.g. dimension value, category, etc.), and data types.

### Create a Config.json

Config.json provides directive to processing engine on how to process the grammar and data files, where they are stored, etc. it should be placed in /ingest/\<state code>/

globals : global settings

dimensions : It includes, file format, location and namespace

programs : program specific settings like namespace, description, input location, output location, dimensions which should be considered etc.

\
Only programs mentioned under config.json will be considered for ingestion.

<figure><img src="https://lh4.googleusercontent.com/94rz7Ht5A0rWOEcm6PWJ6U5RWObR2oMCSJXg0OrwbO8U4DLsUakBg8EZK5VBO01NjKajQrNl-OAa9jzWJ1hNW0OyMzvVQuuKKAYAlQLkR4avrqF_dnmxcNG2Pki_ZFZ_KVtvaPkTvI3aoT8H0z0I_Cg" alt=""><figcaption></figcaption></figure>

### 15.3 Upload the event and dimension grammar spec:

* Convert the Event and Dimension Grammar to JSON format as given in the below example

Example: if there is a event with two columns

school\_id and school\_name

Below would be the JSON object



{

&#x20;    "program": "school-attendance",

&#x20;    "input": {

&#x20;        "type": "object",

&#x20;        "properties": {

&#x20;                        "school\_id": {

&#x20;                                                 "type": "string",

&#x20;                                                 "shouldNotNull": true

&#x20;            },

&#x20;           "school\_name": {

&#x20;                                                   "type": "string",

&#x20;                                                   "shouldNotNull": true

&#x20;            }

}

}



* Dimension grammar : Use the /spec/dimension API to upload the dimension grammar
* Place the dimension grammar file as -dimension.grammar.csv in processing-ms/impl/c-qube/ingest/VSK or NVSK/dimensions/ folder as seen below or as per the config.json settings

<figure><img src="https://lh3.googleusercontent.com/kY4bfdcuNteynNJrD_NsHvdcg8pnobTwhfLB9I_gJkeA9dHrbyrh_P6HtRGT_mF6bVYKyNUFSZ7-gLJ7NYJuH4t0wxJ0LhjDjMTqMdVzU0cv2klQflcQL--llS8Zxu3lgX91Nr9tuS0KW90CpE-PIqI" alt=""><figcaption></figcaption></figure>

**Contents of the district-dimension.grammar.csv**

<figure><img src="https://lh5.googleusercontent.com/aMDK7TGW7ONHajVCISgCURej1h_VirtHq_N_R232ViM-0AKANXGQZ3AmnVAsxp-9BsA9zCN0psm-u1B7Cf1RaWqiASH5txS_Hsh2ZksTO1exiSyGncUYdLQaNhjv-ZWVx5yFsay5gZeMP_it52Sd5Pg" alt=""><figcaption></figcaption></figure>

* Event schema can be ingested in 2 ways:
  * Though API Method

**Event spec API: spec/event**

<figure><img src="https://lh3.googleusercontent.com/DrupXNPiAW9-ZyqMUYteKKKhzhXhSaT3lVJEYxT-LH5ynRqX1SuJQTRTcs_Sgra5fMyv_EAHhm2BMdY1SXgfgDHLRbsiipCBW6r-h1sU5Q8urwgGtE6t2phHbNmqtOa9j_lhf4piljvmuAAnFHW9tl0" alt=""><figcaption></figcaption></figure>

* Through YARN CLI

YARN CLI INGEST

This command is used to ingest Event and Dimension Spec and Dimension Data based on the configuration we have

* Create a \<new-program> folder in processing-ms/impl/c-qube/ingest/\<state\_code>/programs\\
* Place the event grammar file as \<xyz>-event.grammar.csv in processing-ms/impl/c-qube/ingest/\<state\_code>/programs/\<new-program> folder as seen below (example for diksha program)

This would be based on default config.json or else it should be as per config.json

<figure><img src="https://lh4.googleusercontent.com/MXwUFOjitgjvhYpoAzjZIgIVYTYtfcTr_JJ5UK3HIh_v3kM9hYLMx43dXgTn4B5s_FfOUQ-boHcHI8eWWqGtZrRf6bbOcu0ZysRsNnJJGEKxswX4pJ__3Q69vJ0EQxciWl-Vz63N9PTWFou6Df_efrE" alt=""><figcaption></figcaption></figure>

Contents of the district-dimension.grammar.csv

<figure><img src="https://lh4.googleusercontent.com/74XJs0gO8v9HCRYFtj6UYcFqDzXKzk-h-HVnPKh5lMUdE69I6XUtpR7xkQUdM9w39dnwY6pQmwltmUJh_CZxXh0EZeWiZ56ecYHBCvh29embc2s0T8uR0TVXU-XMT28R3z-J3j6QpxyjPBkYtVD3TVg" alt=""><figcaption></figcaption></figure>

### Data Ingestion:

This process may involve uploading the CSV file or connecting to the database directly. Following links will provide more details on the process.

* [Uploading through CSV](broken-reference/)
* [Connecting to Database](broken-reference/)

**Add event data on a regular frequency:** To keep your program up-to-date, continuously add new event data to the platform. Determine an appropriate frequency for updating the data, such as daily, weekly, or monthly.w Ensure that the new data is compatible with the existing event and dimension schema.

### UI Program Addition

* Create a new module manually or using cli common ng g m \<module-name> in the below folder in the angular code base: src/app/views
* Add the folders config and pages, where config holds a configuration file for the reports in this program and pages contains the code of all the tabs/reports.
* Add the routing to the program component in the app-routing module using lazy-loading

<figure><img src="https://lh5.googleusercontent.com/5jp9HOEX24O3pU1qomvK1K-TUm5Tje1cqODomTY9kxwSqgK5paqkyLTaJeVt96H2tqjoMwsu_IPk6LdzgtYuhXJdXiIO2Lp0PbEm_Gx4tQ8_35LdxOL2zcQ5to94LBl9miclCtpV98IU-coMYD4giPw" alt=""><figcaption></figcaption></figure>

* Add the configuration of this program to the main\_matric.csv present in the root folder of query builder.( To add this program to side nav and summary statistics) as shown below.

<figure><img src="https://lh5.googleusercontent.com/C5MX471pQ3wkaeUMxk2b6m-DESKg5eR6DZ98TebG70dJKwe6i6y7GbtP2UWU0xrLRjL62S0iHJQLsDhSadRENe-hxakPhapeLSEcgB88O0r9qOb0Lit2X6hNHrvcD59yZWn7dXw-QWhdlKm6k13b8L4" alt=""><figcaption></figcaption></figure>

* Next add the programId filled in the above file to another file Program Selector in the query Builder root folder itself. The Program Selector file takes input from the ansible during installation to update which programs to be visible in the dashboard. If a new program is added after installation manually fill the programId and set the status true for that program to be visible in the dashboard.

<figure><img src="https://lh3.googleusercontent.com/ZmR3QT4W0BoD2xFvnxxFrBuoP2HlAoyyekf3i7HeG6ixAXUanwUnAA7v3joZvNvX0D2VtAgJqLDS9wZEh1E0dwejin8E83YSCFPhzaPhZpl9A390ABQWlkuAI3kIKMmldBnDdjdao4y2B2sObX6VeA4" alt=""><figcaption></figcaption></figure>

* Configuration file of the newly added program should be added to the below file:

src/app/core/config/configMapping.ts

All the configuration files are mapped at a place for easy access , This object will be used to map each row in main\_metric with program wise configuration files with the respective programIds.

<figure><img src="https://lh5.googleusercontent.com/hzRqczmIjAsrQz6MpSGPmnh6hIVO5_Iq8Hut922WAqTZgh495fPLdnozAsUUynvcZWly-PWhZtL_mFR3560MNxJVCCgtomPa6U0-9x2qTFOAgdqy02cJxra_LIoyGzaGNh9oQQpZR1Shi2QW--_jqSk" alt=""><figcaption></figcaption></figure>

Later one can add the desired KPI to the above program created following the below steps

\\

\\
