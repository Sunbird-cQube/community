# Test for KPIs

By using Pytest Framework : we followed to get the output data from the database and implemented the business logic, and verifying the final result matched to the expected outcome&#x20;

Step 1: Prepare input JSON files for each program(student\_attendance, teacher\_attendance, etc..) which have all the dimensions needed for a particular program along with its values and along with its metric with min and max values.

Step 2:  Use the grammar file required for the program (student\_attendance, teacher\_attendance, etc..) in order to extract the time dimension, dimensions, and metrics.

Step 3: Get the required time dimension and dimensions from the grammar file

Step 4: Get the required metrics from the config file

Step 5: For each metric in the program, generate the test data along with the required dimension columns specified in the config file.

<figure><img src="https://lh5.googleusercontent.com/-slTNSHx-QA_PWsjzA3_BXfqQFPKSwOZ6e0CTzJ9wTJOYXgtAUdRdYHhjjspu2tmREf9sRzXblyaFa1pYqa4-uthkuOBsnzafbvccOvDhdjzzKvYbmXtD9r-S11o_43Zwg4poPngB3Fm1ruSFVBZan0" alt=""><figcaption></figcaption></figure>

Step 6: Split the generated test data of each metric according to different time\_lines (daily, weekly, monthly, yearly) for each dimension key-metric aggregate value combination, to use it as the expected data (which should be filled up through manual calculation).

<figure><img src="https://lh5.googleusercontent.com/lmscir8PsMhD_3WlQKqoGoAH5OIHCqvwpCmK5uLZ-LDrsOPlDI_lTsgSZryPsxXCA1rwMluabhS_9fLh-3bXZnVH0iRSOnd9ahUuyDcIc7eTYU0aQtRnl3RnfwbHqm1Np4hQlkOKiT4Osxpt6Gfos_Q" alt=""><figcaption></figcaption></figure>

<figure><img src="https://lh6.googleusercontent.com/kjWe5RjYbeEufHIWa9OBHICYnoGVx-yVxDnAFVj52UJR8wPGzD31eve9hngsFnPjDgFAfYuokcj_VzGu5gI8b-8PG14u5VobeicAz9DuaB1jSEJ-tyiYkfjP_NaX6jDuENSGDlIUlFaZ0_KHCz8l1fA" alt=""><figcaption></figcaption></figure>

<figure><img src="https://lh3.googleusercontent.com/fo_JJXH2dbsX9AIzMeq2z5g2iKDs0xeAjq9Y2Wlpf5-OISIc7nZr7u3MN6fwo6CJwu8pyIhXWmAnEvXQTH35dQAucT6S0z2gcagiIEpuL1mMOorJUT_AMKyKPMTQkTSvwu2oTCn7VSdO8eSjqk4J4SA" alt=""><figcaption></figcaption></figure>

Step 7: Ingest the test data into the cube server and get the processed data in the database, which is the actual data file.

Step 8: Fill in the aggregate values for expected data manually.

Step 9: Compare the actual data with the expected data and generate the HTML test results.

