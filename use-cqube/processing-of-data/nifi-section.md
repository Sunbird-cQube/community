# Nifi section

Comment start Nifi in cQube is used to create a data flow and automate the processing of data with the help of processor groups. These processor groups are responsible for accessing the data files from the cloud storage and moving it into the processing-ms codebase. Once the data files are moved the commands will be executed which will ingest the data into the database.&#x20;

Here we have different processor groups to process the data(Nifi canvas).\
1\. To run adapters.

2\. To run all programs.

3\. To run program wise.

The Processor groups in nifi can be scheduled using API called [scheduled API ](https://cqube.sunbird.org/use-cqube/ingesting-the-data/steps-to-ingest-data-files/scheduled-api)

<figure><img src="https://lh7-us.googleusercontent.com/RTAA79E4m4LW4kNxJ-x9lqS7LHwui1rMc-m-w4Pjx4UwURcFH9xhzn0xW6H4_CJDE_eyxI-RZNJIYcVLeJzsCOiroK2PXlI8Cdpoq5sDKdW3j6V5KxXoARgNBTzwA72tYx6M4FIr4i1CzhtAkDLn6cw" alt=""><figcaption></figcaption></figure>

**1. To run adapters:** This processor group is used to run the adapters shell script code.

<figure><img src="https://lh7-us.googleusercontent.com/vYOhhEZhqKmGv3WYCUQaPsnNHsHu4JuHhK5IRCXxrNf_O8-KfidyQElnuQb6BJizTMXo0moKHTwQ5KxMWSVGYnuJaLP_ATOw4wNBlhMTCdsz-ufJs-jyJr2QpwxENzKssec2EdeqRZGBHRQof4GRUdM" alt=""><figcaption></figcaption></figure>

<figure><img src="https://lh7-us.googleusercontent.com/1-B6z29UGf5kF5HNL6k9EQxJOJokP2IKIpIbmI6M-m9ERkP4xS1IZ9DtjNd1ccleV5Ig9QawB1oqUjIFfEOeACVQVGuTH4U-9270jHkTm0GsxwLZaB75u76P77-ulwre6OYiOMXKslcu2rE-WPZDdPY" alt=""><figcaption></figcaption></figure>



**2. To run all programs:** This processor group is used to move files from process\_input folder to processing\_ms folder according to folder structures. .i.e., (dimensions/,programs/). Then it will run yarn cli ingest(where it will ingest all schemas and grammars to the database) and yarn cli ingest-data (where it will ingest all data files to the database) commands.

<figure><img src="https://lh7-us.googleusercontent.com/F-AkuAxqcUxj4Lko-3lnAficTq2tDQh_x_GXKCdPsqy4ZJUvozqRMRS3fCtFplDC-R8qDtwdcvJ19phlJGY77UqIZ75cB0gi_DiuSYCvtIu8oH6lwTbO0K2O6UlcXbYM8MDEJ4SZg09S0dGBkbwuxbs" alt=""><figcaption></figcaption></figure>

**3.To run program wise:** This processor group is used to move particular program files from process\_input folder to processing\_ms folder. Then it will run yarn cli ingest and yarn cli ingest-data --filter=’program\_name’.(where it will ingest particular program data files).

In order to automate these processor groups we have written REST-APIs

<figure><img src="https://lh7-us.googleusercontent.com/WLJMhDjsBMTveEgWHBrLVTNqb62DdiRsrxyh2K_TRdnxWVb29xnKDv5r2fnKkV3bfAa9ekyK4kR-vLIRtPQXpNOtxdDEer7prp24KTK3NKkt-vMYn8Tu0EiBPivT_tjnsV63iKYHhZQ_2YsOXd5VKsQ" alt=""><figcaption></figcaption></figure>
