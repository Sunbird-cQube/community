# Scheduled API

This API helps to schedule the processor group at any particular time.

### Step 1:&#x20;

Open the specified request & add the details

**API Endpoint:** \<domain\_name>/api/spec/schedule

**HTTP Method:** POST

<figure><img src="https://lh4.googleusercontent.com/NB-aZ4e20WfpPJlzzv9tuYarjLxYkCJ2bfimAFeiABrjSxYTc4TrRuLWslRhMsDbUpRcYqhvXH9o61IoFh2lqmgSw7jHwS2IwNZCemmt_TqrTOR0Rdh-b2UqTIq4mK0RJLxMkWFSq-Fp79lkBpjHYwQ" alt=""><figcaption></figcaption></figure>

### Step 2:&#x20;

Build the request body with reference to YAML file. The request body for the above api is attached in Link for yaml:[ <img src="https://lh6.googleusercontent.com/6iHBv7-J6xyy-5gQJP5LFct6CCSQtWwle7mfLmderwHe8v6_YMtGn_fu6PStM26dCx9TCW2Cqczakl5bTHifrH-LWpnUHrCyJbcIUcY6qKS2tvJqc4eOxtgSbk6-cw_i_XznwisTSBuwldWvQFP1WLU" alt="" data-size="line">spec-ms/spec.yaml at dev · Sunbird-cQube/spec-ms](https://github.com/Sunbird-cQube/spec-ms/blob/dev/spec.yaml)   . Provide the valid input details for the Parameters shown below.&#x20;

<figure><img src="https://lh4.googleusercontent.com/jRI10tM1uT30UwtTaCoFaADJ_Ye_F5eASi_PU3nTA9OhJ1vT1Ct_ahXYLuCn8mmPUTdBxlp2QGQN6gvhto7G1SH_Et8RbOFD0fUGr10pYCyamczk5DGimoOO5todVMI0JB-hHnBhpWAqA5v6OtuG-NQ" alt=""><figcaption></figcaption></figure>

### Step 3:&#x20;

Click on the send button for the request and if the request is successful the user should see a response message. The schedule time will be updated in the processor group.

<figure><img src="https://lh5.googleusercontent.com/FcloJ0J3uWjLSAzzPJG5UyOSJnVKHiJ7rzbZGvafXUfRkYL3c-wxwsaQM4Xp2qbEZydGexoi23ndSVFzAVQSAIkjVB0-B6BEM-iMRQZl77Dcj0Q3o5Dm2Q9cugPCRRQo9tskb6dioeBVMBpm_LEjGAw" alt=""><figcaption></figcaption></figure>

The schedule api helps to run the processor group in Nifi at a scheduled time. The schedule time can be updated by changing the cron expression for scheduled\_at property in the request body.

**Processor Group state Change API:**

This API helps to change the state of a processor group in Nifi. It will provide the functionality to start the processor group or stop the processor group.

**Step 1:** Create  a specified request in postman  and add the details.

<figure><img src="https://lh7-us.googleusercontent.com/DUbTnb-ysYYg0xEfdQ9PUfOjlgHQtqOUBWfPYeP2V0vvIZCDZiSBKLOzVAsCMXNCHqa1U4A1hQNERHuRFuLeTMsOg9YgsR6w7TjbBRNQ9GdXVdluF5sZ0azvaPdl8OOEQkENCQHXZxtjd5doubzt8hg" alt=""><figcaption></figcaption></figure>

**Step 2:** Step 2: Build the request body with reference to YAML file. The request body for the above api is attached in Link for yaml:[ <img src="https://lh7-us.googleusercontent.com/qMa3emhWmrFwRvUTkiQ2q6CTtXbsK8PIdipItYpsUr3HhNR-_V6qiNWE0GQVt-cd48WOMBVEkeIc2XS0nCO4evRngYks1dhVYwi2bvNlAT9EtDmrzzMr0Q6lzbrG_ErLLGnrFSthZpYXrf0NgJ4d6B4" alt="" data-size="line">spec-ms/spec.yaml at dev · Sunbird-cQube/spec-ms](https://github.com/Sunbird-cQube/spec-ms/blob/dev/spec.yaml)   . Provide the valid input details for the Parameters shown below.\


<figure><img src="https://lh7-us.googleusercontent.com/4muG8rfsdrBueNhcp8CUeBf-4JHyIO7-K-_dY7un7aqgkv4v-DplFXNt9OvPWEBwYelLjXM_A4ezqnOKDnuQScav6OtjYZWN6HdZxtt0t7v34NAFh1P3rldBLZA34YNL17uUyapT1xAtl-2Y5A3OzCI" alt=""><figcaption></figcaption></figure>

&#x20;**Step 3:** Click on the send button for the request and if the request is successful the user should see a response message.&#x20;

<figure><img src="https://lh7-us.googleusercontent.com/8jDYjaK9n0OCK9DSbiObVMael4Yjg53hopfSQan9mdPDDgDuVhrA3RH9x2ixFCqJwVaI5F7igNXBDWZ79xRL4CbYJVcICtFSJgPZTlXnLUmBKUjzaEkoE-9YL6Rk3BFjGHCKsBEu9wa02rwcPWm3KRY" alt=""><figcaption></figcaption></figure>

In the above example as you can see the processor group onestep\_dataingestion\_aws is changed to running state.\
Note:

1\. This API is only used to change the state of a processor group. If you want to change the schedule time you will have to use the Schedule API.

2\. It is suggested to stop the processor groups once the data is ingested for all the programs using the above API

\
\
