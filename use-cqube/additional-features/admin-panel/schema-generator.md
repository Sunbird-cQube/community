# Schema Generator

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

<figure><img src="https://lh7-us.googleusercontent.com/R6NULK18Gu7HLMjUDGqW3XRRWeCQa80WACcnLXSTMIJgzFFMoJuRSHUAmNDK3WrO1AUQdny6kRvbgq6TV2OXitWI9iXgqUyZOJvhLOPUGfgYZ3dxt770Wtadn-puewihWu8tOSiiT6hnx0_Ccn40Fhc" alt=""><figcaption></figcaption></figure>

Following is the sample data for the ETB coverage status data of the DIKSHA program.

<figure><img src="https://lh6.googleusercontent.com/Ar7ZqUCH7uC5Jr_Y2JpuplaEenmJx0P0uIDeamXSeeDKBO5QgXLjLFEXbqMp_l82bsGyFbMOKEjyEOL2P4cU_oyi9NEfbI7mvLddMlkZBTwf1_R5zl3ZT10nKHIGor89B-2lffdoTLdsEOAjg6gnOcw" alt=""><figcaption></figcaption></figure>

Once the user uploads the file, the extracted schema will be shown to the user in the format of the table. The following screenshot represents the sample screen.

<figure><img src="https://lh7-us.googleusercontent.com/inrPqECLI2vJFEXWPX_nX9-nwgIfFRoJdxA_wXbj-ZPBeDlh3DADHORKoR_HjJTVCoUsid29WOdFs34JC8pUne78-SP6gnTRLn0bNh6TYvZFR852QQsCC1DWHRAdmAV8G55BXdO_MM-8Kf8CDQ0Sd_0" alt=""><figcaption></figcaption></figure>



The user needs to be able to enter a program name and description, and choose whether the field should be treated as a metric or not. The field types are also shown in the table for every field. Users can edit the name of the field if they want and those field names are editable in the table.

Along with the above, users are also able to select dimensions as well. Here’s the screenshot of another part of the screen that contains adding Dimensions.

Note: Automatically date time fields are considered as time dimensions.

<figure><img src="https://lh7-us.googleusercontent.com/wQAkHh_-cmIhtbvs1i-UwBP6VgSmJJ3ckkBSEhnG3yf6CZCqPHMUYRWcu-eVTgYrRFFwKH1n8wVTnHCnu90Xkeg8s9OO7lPxqn4zAJNaCDFgGEwQNUjNWUm4SraVtp-UxVWH_MxBlfMaDqytb7FJ7o4" alt=""><figcaption></figcaption></figure>

Users will be able to add Dimensions as shown in the above screenshot. By clicking on the “Add Dimension” button, users can add a new dimension for the event. After adding the dimension, the user needs to add at least one field from the event to the dimension. If the user adds more than one field to the dimension, then the user has to define at least one field as “Index”. Indexes are useful in removing the duplicates from the records while generating the dimension files.

Note: If the user only selects one field for the dimension, then no need to define the Index field as the selected field would be considered as the Index for that dimension.

After providing the required inputs, users can be able to generate dimensions and events by clicking on the above “Update” button.

\


2. After generating the dimension and event grammars for the provided file, the following screen will be displayed to the user.

<figure><img src="https://lh3.googleusercontent.com/nENtiN36DVUufT1K_qaTHAwComQ66pnqNjdtNpqHRlfBfXoUKIlOFolN4Tw2ySDP5Du_nKcUkTJwe-xVwI_UsPk07h9oJ3Rvkfa4V6Yl49MY5GHBwNCFYPyAX_YyAYGz6d0ARJ_2JTP65lWSesV3Jzk" alt=""><figcaption></figcaption></figure>

The screen has navigation buttons at the top that the user can use to switch between the dimensions and events tabs. The list tab contains information about the dimensions and metrics list.

The dimensions tab contains a drop-down menu that the user can use to select the dimension they want to see.

<figure><img src="https://lh4.googleusercontent.com/lB9KURorRu__hfQuDeNuIueAwBXyuOHASjs3Qow9WdGCiE9xFDOWDzVrJwSOu0aV_hgjB6L0iJYknQePow_vYlZWfxUxgeCie19wCtLdNQS_d8uidBC8m_FwLxZIvCqWpR0a4xyx5cLA7ktIBiUH6MQ" alt=""><figcaption></figcaption></figure>

The events tab contains a dropdown menu that the user can use to select the event they want to see.

<figure><img src="https://lh7-us.googleusercontent.com/Gq1MNe1uw0Myi0jM9SUhQoxQFIqKffkA9d-6tJ7CdwjvDu0Xcy_N8fdx2Z-qhw5VMMIDpwI30WaDpJRL6QJ4rmAKgY9L_SqbpQWkH2ojUwMlx__FIl-xOFs2OKA-YVIet12k0o18Tt_sszZ3hauFuJc" alt=""><figcaption></figcaption></figure>

The user will be able to download all the generated files in zip format by using the “Download Ingest” button.
