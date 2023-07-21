# Schedule API

This API helps to schedule the processor group at any particular time.

### Step 1:&#x20;

Open the specified request & add the details

**API Endpoint:** \<domain\_name>/api/spec/schedule

**HTTP Method:** POST

<figure><img src="https://lh3.googleusercontent.com/ZO7ofwg2wyyiypA1MJrGzXHZjGvGM3mfXeWJuNqh76ufzYKnc6gXLDxmA74Z5YjnoyXwsy6yvNdB_vZPRFZsXU0feZtd8F846nzB0tDaWIeHBrjbcWTdfnjaJSTL2jACkq4FOvfK3PSksVsfAyqtjmY" alt=""><figcaption></figcaption></figure>

### Step 2:&#x20;

Build the request body with reference to YAML file. The request body for the above api is attached in Link for yaml:[ <img src="https://lh6.googleusercontent.com/6iHBv7-J6xyy-5gQJP5LFct6CCSQtWwle7mfLmderwHe8v6_YMtGn_fu6PStM26dCx9TCW2Cqczakl5bTHifrH-LWpnUHrCyJbcIUcY6qKS2tvJqc4eOxtgSbk6-cw_i_XznwisTSBuwldWvQFP1WLU" alt="" data-size="line">spec-ms/spec.yaml at dev · Sunbird-cQube/spec-ms](https://github.com/Sunbird-cQube/spec-ms/blob/dev/spec.yaml)   . Provide the valid input details for the Parameters shown below.&#x20;

<figure><img src="https://lh4.googleusercontent.com/jRI10tM1uT30UwtTaCoFaADJ_Ye_F5eASi_PU3nTA9OhJ1vT1Ct_ahXYLuCn8mmPUTdBxlp2QGQN6gvhto7G1SH_Et8RbOFD0fUGr10pYCyamczk5DGimoOO5todVMI0JB-hHnBhpWAqA5v6OtuG-NQ" alt=""><figcaption></figcaption></figure>

### Step 3:&#x20;

Click on the send button for the request and if the request is successful the user should see a response message. The schedule time will be updated in the processor group.

<figure><img src="https://lh6.googleusercontent.com/3UfNZsRB6UcsNPD3F0JMU6pJRZDp19b5-y4646IdHY8GlvQ48ZZf42GyFZs1vBFEoMq9m_T8eaIh9-SJVnreMVg0DWWC_yKLOY7dqaXonKph5drsDN7dHRQ5XUZs90Oc7RYa7PRSy_aKfd9Je9qUYco" alt=""><figcaption></figcaption></figure>

The schedule api helps to run the processor group in Nifi at a scheduled time. The schedule time can be updated by changing the cron expression for scheduled\_at property in the request body.

\
