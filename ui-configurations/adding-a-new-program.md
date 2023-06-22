---
description: Explains the process to add a new program into cQube Ed
---

# Adding a New Program

### Create event and dimension Grammar files:&#x20;

Design the event and dimension grammar files for your program. This grammar defines the structure and relationships between different data elements, such as event attributes and dimensions.

* Event grammar: The event grammar defines the structure of the events to be ingested into the system. It includes information such as the event name, its attributes (e.g. event timestamp, user ID, etc.), and data types.
* Dimension grammar: The dimension grammar defines the dimensions, or attributes, that will be used to group and filter events. It includes information such as the dimension name, its attributes (e.g. dimension value, category, etc.), and data types.

### Create a Config.json

Config.json provides directive to processing engine on how to process the grammar and data files, where they are stored, etc. it should be placed in /ingest/\<state code>/&#x20;

globals : global settings

dimensions : It includes, file format, location and namespace

programs : program specific settings like namespace, description, input location, output location, dimensions which should be considered etc.

\
Only programs mentioned under config.json will be considered for ingestion.

<figure><img src="https://lh4.googleusercontent.com/94rz7Ht5A0rWOEcm6PWJ6U5RWObR2oMCSJXg0OrwbO8U4DLsUakBg8EZK5VBO01NjKajQrNl-OAa9jzWJ1hNW0OyMzvVQuuKKAYAlQLkR4avrqF_dnmxcNG2Pki_ZFZ_KVtvaPkTvI3aoT8H0z0I_Cg" alt=""><figcaption></figcaption></figure>

### 15.3 Upload the event and dimension grammar spec:

* Convert the Event and Dimension Grammar to JSON format as given in the below example

Example: if there is a event with two columns

&#x20;   school\_id and school\_name&#x20;

Below would be the JSON object

\


{

&#x20;    "program": "school-attendance",

&#x20;    "input": {

&#x20;        "type": "object",

&#x20;        "properties": {

&#x20;           "school\_id": {

&#x20;              "type": "string",

&#x20;              "shouldNotNull": true

&#x20;            },

&#x20;           "school\_name": {

&#x20;                "type": "string",

&#x20;               "shouldNotNull": true

&#x20;            }

}

}\


* Dimension grammar : Use the /spec/dimension API to upload the dimension grammar
* Place the dimension grammar file as \<xyz>-dimension.grammar.csv in processing-ms/impl/c-qube/ingest/\<state\_code>/dimensions/ folder as seen below or as per the config.json settings

<figure><img src="https://lh3.googleusercontent.com/kY4bfdcuNteynNJrD_NsHvdcg8pnobTwhfLB9I_gJkeA9dHrbyrh_P6HtRGT_mF6bVYKyNUFSZ7-gLJ7NYJuH4t0wxJ0LhjDjMTqMdVzU0cv2klQflcQL--llS8Zxu3lgX91Nr9tuS0KW90CpE-PIqI" alt=""><figcaption></figcaption></figure>

**Contents of the district-dimension.grammar.csv**

<figure><img src="https://lh5.googleusercontent.com/aMDK7TGW7ONHajVCISgCURej1h_VirtHq_N_R232ViM-0AKANXGQZ3AmnVAsxp-9BsA9zCN0psm-u1B7Cf1RaWqiASH5txS_Hsh2ZksTO1exiSyGncUYdLQaNhjv-ZWVx5yFsay5gZeMP_it52Sd5Pg" alt=""><figcaption></figcaption></figure>

* Event schema can be ingested in 2 ways: &#x20;
  * Though API Method

**Event spec API: spec/event**

<figure><img src="https://lh3.googleusercontent.com/DrupXNPiAW9-ZyqMUYteKKKhzhXhSaT3lVJEYxT-LH5ynRqX1SuJQTRTcs_Sgra5fMyv_EAHhm2BMdY1SXgfgDHLRbsiipCBW6r-h1sU5Q8urwgGtE6t2phHbNmqtOa9j_lhf4piljvmuAAnFHW9tl0" alt=""><figcaption></figcaption></figure>

* Through YARN CLI

YARN CLI INGEST

This command is used to ingest Event and Dimension Spec and Dimension Data based on the configuration we have

* Create a \<new-program> folder in processing-ms/impl/c-qube/ingest/\<state\_code>/programs\

* Place the event grammar file as \<xyz>-event.grammar.csv in processing-ms/impl/c-qube/ingest/\<state\_code>/programs/\<new-program> folder as seen below (example for diksha program)

This would be based on default config.json or else it should be as per config.json

<figure><img src="https://lh4.googleusercontent.com/MXwUFOjitgjvhYpoAzjZIgIVYTYtfcTr_JJ5UK3HIh_v3kM9hYLMx43dXgTn4B5s_FfOUQ-boHcHI8eWWqGtZrRf6bbOcu0ZysRsNnJJGEKxswX4pJ__3Q69vJ0EQxciWl-Vz63N9PTWFou6Df_efrE" alt=""><figcaption></figcaption></figure>

Contents of the district-dimension.grammar.csv

<figure><img src="https://lh4.googleusercontent.com/74XJs0gO8v9HCRYFtj6UYcFqDzXKzk-h-HVnPKh5lMUdE69I6XUtpR7xkQUdM9w39dnwY6pQmwltmUJh_CZxXh0EZeWiZ56ecYHBCvh29embc2s0T8uR0TVXU-XMT28R3z-J3j6QpxyjPBkYtVD3TVg" alt=""><figcaption></figcaption></figure>

### Data Ingestion:&#x20;

This process may involve uploading the CSV file or connecting to the database directly. Following links will provide more details on the process.

* [Uploading through CSV](broken-reference)
* [Connecting to Database](broken-reference)

**Add event data on a regular frequency:** To keep your program up-to-date, continuously add new event data to the platform. Determine an appropriate frequency for updating the data, such as daily, weekly, or monthly.w Ensure that the new data is compatible with the existing event and dimension schema.

\
