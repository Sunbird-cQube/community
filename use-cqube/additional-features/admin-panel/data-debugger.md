# Data Debugger

It analyzes the data and reports the user about the errored records in the raw data file of an event or dimension. User has to select an event or dimension schema which is needed to validate the records of uploaded events or dimension files. After that debugger will analyze the uploaded data against the selected schema and it reports back to the user with the errored records. This feature helps the user to analyze the data before ingesting the data for data processing.

Data Debugger analyzes the fed data and reports and identifies the errors in them, if any, in an event or dimension files.&#x20;

Following  screenshot for the  data debugger.

<figure><img src="broken-reference" alt=""><figcaption></figcaption></figure>

Steps to validate the Raw Data file:&#x20;

(Please note - The raw data file should be in CSV format.)

1. Check 'Dimension Grammar' is present in the dropdown menu.
2. Upload the dimension file.
3. Click on the 'Validate Grammar' Tab.

Now, the system will show errors if any, in the screen for the uploaded file. If the file does not contain any errors, the user will be directed to the next screen.&#x20;



Here are more information about each step above.&#x20;

1. **Upload the grammar file for the dimension or event that you want to validate.**

The grammar file is a CSV file that defines the structure of the data that you want to validate. It contains information about the different fields in the data, such as the field name, data type, and constraints.

Following  screenshot of validate grammar of data debugger

<figure><img src="broken-reference" alt=""><figcaption></figcaption></figure>

Following is the sample grammar file block dimension:

![](https://lh4.googleusercontent.com/E7XutNio5PHiOX1SsgOdA-6hM3kOMMjGN-8CzepJPcDtlS1N8HVB0vVsb86uCtcbFm\_8MCngRAXi88P\_0obkuNJ47UASe8wpJF5jA3jVrjqKyeXhxUgIkORPhRCq3Dvs2VyZq2FR\_plfzY4ijmUmD3U)

**Note**: Include primary key if it is a dimension grammar file.



2. **Validate the grammar file.**

Once you have uploaded the grammar file, you need to validate it to make sure that it is correct. The validation process will check for errors in the grammar file, such as missing fields or invalid data types.

Here is a sample screenshot of a table that might be displayed to the user:

<figure><img src="https://lh3.googleusercontent.com/FIW-TicihbEBaXCx_zthE6ix4lLlC5522rZAjg1yA0CLMwj2YEIsO7S3u9UbExgmV3vxuclYq53ZTHnd_c9RZoMSRtHIyKpWAbkTDRg7duCnoqZxioLuVkzXG7nUlmM6FtdaNbF0sGI-E8M_ktaA8l8" alt=""><figcaption></figcaption></figure>

If the uploaded grammar file is valid, then a Validate Data button will be enabled for the user. Using the Validate Data button, the user can go into the validation step.

Following screenshot will be displayed to the user

<figure><img src="https://lh6.googleusercontent.com/5oS8SWuHUwwK7oXRideOp0RLbcG-O7gfPEqai_nyscUFMDG-lLHfbEmR3B_GONV9nwTOwEUrf2gcLGIrBVTqdgWlFUx3BLIUYU0bKE69yf1OZOVHV71rXCcd1neN8Gn9dIQFkWqWV9yE_h5KmWOvH-M" alt=""><figcaption></figcaption></figure>

3. **Validate the raw data against the uploaded grammar file.**

Once the grammar file has been validated, you can validate the raw data against it. The validation process will check for errors in the raw data, such as missing fields or invalid values.

If there are no errors in the raw data file, then the validation will be successful. Otherwise, the validation will fail, and you will be given a report of the errors.

Following screenshot for validate the data

<figure><img src="https://lh4.googleusercontent.com/PHkWBe8aPy8YzWBQTtDqPwv2nofWCpEYNiwvzGYd5rm-eLSuROPCYYd7Zs61ehmc0AHHxrNOO3KFR-DAAsNAj6zAjGnmBPidkC3t0LNTgf2GAxBGipuEGGhquxa6oSTI6hEwabdAMN7sLrkCJCqJvH4" alt=""><figcaption></figcaption></figure>

If there are any errors in the uploaded data, then the errors will be reported to the user in the form of a table. Following is a screenshot of the error screen.

<figure><img src="https://lh5.googleusercontent.com/VQj_cRUb7PcZfukb-KWB7wASOjrvp8hgr0ZxHTCQ55FeaMrnYw-S5QEn5pnEHI-IGyK-F2v89U99YVAQHhWgrKKCP90crH6qiLjbYn69-ijZYsPBB__jhRqr5eOzCXKprKv2Ee3HT6muYYWp3HwcXxs" alt=""><figcaption></figcaption></figure>

\


<figure><img src="https://lh4.googleusercontent.com/LxHvoHAUjoqQ_2RdJPoVcKVTQMnJhJNJP2_XsNUGMHxjAd_la7_PTYGCfG0B1KI0g-tr8862Twla0kDtQionJyj8Rqw2mYFiEDpn5hiHOXr3AS9qmZah4AyBS6L_tdwslghY2Uj92Ktxk2u6z19yUOE" alt=""><figcaption></figcaption></figure>

**Steps:**

* **Grammar Validation**

The user must first choose the grammar file type to validate, either dimension or event. Then, the user must upload the grammar file. After uploading the file, the debugger analyzes the grammar and reports any errors to the user. If there are no errors, the debugger shows a message indicating that the schema is valid.

* **Data Validation**

The user must first choose the data file type to validate, either dimension or event. Then, the user must upload the raw data file. After uploading the file, the debugger analyzes the data against the grammar uploaded in the previous step and reports any errors to the user. If there are no errors, the debugger shows a message indicating that the schema is valid.\
