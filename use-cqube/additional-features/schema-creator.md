# Schema creator

Schema generator is a tool that can generate a schema for given set of data. This schema can then be used to validate the data and to generate code to work with the data.

In the context of  raw event data, the schema generator can be used to generate a grammar file and a dimension file. The grammar file defines the structure of the event data, while the dimension file defines the different dimensions of the event data.

These files could then be used to validate the event raw data and to generate code to work with the data. For example, the grammar file could be used to validate the event data against a schema. The dimension file could be used to generate a database schema or to generate code to load the event data into a data warehouse.

Here is an example of how a schema generator could be used to generate a grammar file and a dimension file for event raw data:

1. The user provides the schema generator with a sample of the event raw data.
2. The schema generator analyzes the data and generates a schema.
3. The user reviews the schema and makes any necessary changes.
4. The user generates the grammar file and the dimension file.
5. The user validates the event raw data against the grammar file.
6. The user generates code to load the event data into a data warehouse using the dimension file.

Schema generators are a valuable tool for working with event raw data. They can help to ensure that the data is well-structured and easy to use.

Steps :&#x20;

1. Upload the sample event data CSV file. This file will be used by the schema generator to extract the schema and derive the dimensions.
2. Review the schema list of fields and field types. The schema generator will display a list of fields and their types as either dimensions or metrics. You can update the field types if needed.
3. Click the update button to generate the grammar and dimensions for the given event.

Once the schema and dimensions have been generated, you can download them in a zip file. This file will contain two files: a grammar file and a dimension file.

The grammar file defines the structure of the event data. The dimensions file defines the different dimensions of the event data.

You can then use these files to validate your event raw data and generate code to work with the data. For example, you could use the grammar file to validate your event data against a schema. You could use the dimensions file to generate a database schema or to generate code to load your event data into a data warehouse.

Here are some additional tips for using a schema generator:

* Make sure that the sample event data file that you upload is representative of the entire event data set. This will help to ensure that the schema and dimensions that are generated are accurate.
* Review the schema list of fields and field types carefully before clicking the update button. This will help to ensure that the schema and dimensions are generated correctly.
* Once you have generated the schema and dimensions, test them with a small sample of your event raw data to make sure that they are working correctly.

&#x20;**Example:**

1. Upload the sample event data CSV file. This file will be used by the schema generator to extract the schema and derive the dimensions.

Following  screenshot of the schema generator.

<figure><img src="broken-reference" alt=""><figcaption></figcaption></figure>

Following is the sample data for the ETB coverage status data of the DIKSHA program.

<figure><img src="https://lh6.googleusercontent.com/Ar7ZqUCH7uC5Jr_Y2JpuplaEenmJx0P0uIDeamXSeeDKBO5QgXLjLFEXbqMp_l82bsGyFbMOKEjyEOL2P4cU_oyi9NEfbI7mvLddMlkZBTwf1_R5zl3ZT10nKHIGor89B-2lffdoTLdsEOAjg6gnOcw" alt=""><figcaption></figcaption></figure>

Once the user uploads the file, the extracted schema will be shown to the user in the format of the table. The following screenshot represents the sample screen.

<figure><img src="https://lh4.googleusercontent.com/zJ0j0zvV11vtYWT14aDutF_f7Cc6B6TiNsBy0n7MZ39woiTt7mylUF-cQ_1ovJHmHqBiCrAp1EmWX37NtIecYHWy0xmIZ0-w-lje36J5d0D8HFdCZbsZaib2G0Sm-PeGqx7TaGUnyerI0okz4NTF2DI" alt=""><figcaption></figcaption></figure>

The user needs to be able to enter a programme name and description and choose whether the dimension field should be treated as a dimension or a metric. The field type selection can be used to group or filter data or to calculate statistical measures. After selecting the required inputs, users can generate dimensions and events by clicking on the "Update" button above.

2. After generating the dimension and event grammars for the provided file, the following screen will be displayed to the user.

<figure><img src="https://lh3.googleusercontent.com/nENtiN36DVUufT1K_qaTHAwComQ66pnqNjdtNpqHRlfBfXoUKIlOFolN4Tw2ySDP5Du_nKcUkTJwe-xVwI_UsPk07h9oJ3Rvkfa4V6Yl49MY5GHBwNCFYPyAX_YyAYGz6d0ARJ_2JTP65lWSesV3Jzk" alt=""><figcaption></figcaption></figure>

The screen has navigation buttons at the top that the user can use to switch between the dimensions and events tabs. The list tab contains information about the dimensions and metrics list.

The dimensions tab contains a drop-down menu that the user can use to select the dimension they want to see.

<figure><img src="https://lh4.googleusercontent.com/lB9KURorRu__hfQuDeNuIueAwBXyuOHASjs3Qow9WdGCiE9xFDOWDzVrJwSOu0aV_hgjB6L0iJYknQePow_vYlZWfxUxgeCie19wCtLdNQS_d8uidBC8m_FwLxZIvCqWpR0a4xyx5cLA7ktIBiUH6MQ" alt=""><figcaption></figcaption></figure>

The events tab contains a dropdown menu that the user can use to select the event they want to see.

<figure><img src="https://lh4.googleusercontent.com/dbjuwo8HvcDYMymFdotMO3izaEn3lV45RFBCyHTXo9-n8EXF6LPMUw9AbF_cvP7ZFD0bdhYombS7jFcCWoKsPyzvWgjtOpt4YyCsD9JLjyRYHJbbhQcVy_umVpinpmBM5Ha-zQYvbfkkPyh3Vc2MM6o" alt=""><figcaption></figcaption></figure>

The user will be able to download all the generated files in zip format by using the “Download Ingest” button.
