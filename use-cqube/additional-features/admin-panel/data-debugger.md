# Data Debugger

It analyzes the data and reports the user about the errored records in the raw data file of an event or dimension. User has to select an event or dimension schema which is needed to validate the records of uploaded events or dimension files. After that debugger will analyze the uploaded data against the selected schema and it reports back to the user with the errored records. This feature helps the user to analyze the data before ingesting the data for data processing.

Data Debugger analyzes the fed data and reports and identifies the errors in them, if any, in an event or dimension files.&#x20;

**How it works:**

To validate the raw data of either dimension or an event, first:

1. Upload the grammar file for the dimension or event that you want to validate.
2. Validate the grammar file.
3. Validate the raw data against the uploaded grammar file.

**Steps to validate the Raw Data file:**&#x20;

(Please note - The raw data file should be in CSV format.)

1. Check 'Dimension Grammar' is present in the dropdown menu.
2. Upload the dimension file.
3. Click on the 'Validate Grammar' Tab.

Now, the system will show errors if any, in the screen for the uploaded file. If the file does not contain any errors, the user will be directed to the next screen.&#x20;



Here are more information about each step above.&#x20;

1. **Upload the grammar file for the dimension or event that you want to validate.**

The grammar file is a CSV file that defines the structure of the data that you want to validate. It contains information about the different fields in the data, such as the field name, data type, and constraints.

Following  screenshot of validate grammar of data debugger

<figure><img src="https://lh7-us.googleusercontent.com/-mkkkFxHJgnam06-Hf4xB1BTIPZX8JwXnVev-kyfbXOXUQP8zW7mfVs8C9wpoBURWmkS5RDgZm_vavsnQH6noi9pzlMrzU9QUcUpmAXQ_RG-u2obigDwboaaQtNyaQ0oH_mAbTLftzXgiZquyJRD-ZM" alt=""><figcaption></figcaption></figure>

Following is the sample grammar file block dimension:

<figure><img src="https://lh4.googleusercontent.com/E7XutNio5PHiOX1SsgOdA-6hM3kOMMjGN-8CzepJPcDtlS1N8HVB0vVsb86uCtcbFm_8MCngRAXi88P_0obkuNJ47UASe8wpJF5jA3jVrjqKyeXhxUgIkORPhRCq3Dvs2VyZq2FR_plfzY4ijmUmD3U" alt=""><figcaption></figcaption></figure>

**Note**: Include primary key if it is a dimension grammar file.



2. **Validate the grammar file.**

Once you have uploaded the grammar file, you need to validate it to make sure that it is correct. The validation process will check for errors in the grammar file, such as missing fields or invalid data types.

Here is a sample screenshot of a table that might be displayed to the user:

<figure><img src="https://lh3.googleusercontent.com/FIW-TicihbEBaXCx_zthE6ix4lLlC5522rZAjg1yA0CLMwj2YEIsO7S3u9UbExgmV3vxuclYq53ZTHnd_c9RZoMSRtHIyKpWAbkTDRg7duCnoqZxioLuVkzXG7nUlmM6FtdaNbF0sGI-E8M_ktaA8l8" alt=""><figcaption></figcaption></figure>

If the uploaded grammar file is valid, then a Validate Data button will be enabled for the user. Using the Validate Data button, the user can go into the validation step.

Following screenshot will be displayed to the user

<figure><img src="https://lh7-us.googleusercontent.com/sH3nVYHfOpopGhRZ03lBCbn-vAXoCyK7Y_Qz4wlx_NlKKJBjRleu_bIBM6nh086H-GFnuLONTAZJ7nD8ZZarynPEobKqTccOE1zYv8SxDDL5kTnklXJA636f5M5n5Q-vo5omoJd0uLmV0-8NwOWYluw" alt=""><figcaption></figcaption></figure>

3. **Validate the raw data against the uploaded grammar file.**

Once the grammar file has been validated, you can validate the raw data against it. The validation process will check for errors in the raw data, such as missing fields or invalid values.

If there are no errors in the raw data file, then the validation will be successful. Otherwise, the validation will fail, and you will be given a report of the errors.

Following screenshot for validate the data

<figure><img src="https://lh7-us.googleusercontent.com/8Qh_qyyzxBs-56hFhH6S4D3KqRG_54tojwBvf1EM7XgVgV0cDOEYS_bnJ9BPsWE2eQ-WQQkQEouo7tnN4SXLOt5lBfdYlKAbfr2TNUL18lWrPkam873ycP_mYmVoUZvfCOtOGnkd9D4G7hC0f4CtoYM" alt=""><figcaption></figcaption></figure>

If there are any errors in the uploaded data, then the errors will be reported to the user in the form of a table. Following is a screenshot of the error screen.

<figure><img src="https://lh7-us.googleusercontent.com/ZglCSoRa-h3u-5Y8Ejqenilfj0FJHCYkAoBqz8PKJUg3GbaqpWXlgoLfUkYn2lrjcdW6qu5nZa3Qa0B0xBTaXDbNG-p7csPi3ZH6jWjREYBTrfakgA-LQHSZT5jNaEQ2zGEpMyYkylvy8l4CEaFba9U" alt=""><figcaption></figcaption></figure>

\
If the file is valid, then a alert message  will be displayed to the user, which means that the data is ready to be ingested. Following is the screenshot:

<figure><img src="https://lh7-us.googleusercontent.com/jDZtQHs2PIanm81-8_hqjNw6SbtZ1e2duniZcQACNDpzJkqBI-m6Oi7axqNw--9EENKja2hy35KAjw-ux0NI9s6VkTUSvaKnyzw4HJypTzkYOeplKYZSksvapXd5zjEtvl2QktKTqIMhVZjng77GZsE" alt=""><figcaption></figcaption></figure>

\


**Steps:**

* **Grammar Validation**

The user must first choose the grammar file type to validate, either dimension or event. Then, the user must upload the grammar file. After uploading the file, the debugger analyzes the grammar and reports any errors to the user. If there are no errors, the debugger shows a message indicating that the schema is valid.

* **Data Validation**

The user must first choose the data file type to validate, either dimension or event. Then, the user must upload the raw data file. After uploading the file, the debugger analyzes the data against the grammar uploaded in the previous step and reports any errors to the user. If there are no errors, the debugger shows a message indicating that the schema is valid.\
