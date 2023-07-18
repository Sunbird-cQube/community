# GET File status API

### Step 1: &#x20;

Open the specified request & add the details

**API Endpoint:** \<domain\_name>/ingestion/file-status

**HTTP Method:** GET&#x20;

<figure><img src="https://lh5.googleusercontent.com/1YphsKY7igb8r4DOXpCdiBCBieQq36dbnDx6nDq4MBzGjI6Ko-4hDnylAwDVnoqJl6FgFVn7qXA7QOtyfDr5kKacLMct8n82K2ETjMe3bwOi5LLm5gw04eKHLhV11VGMsnoQ9SAbLbo6CeLZMcCFl5k" alt=""><figcaption></figcaption></figure>

### Step 2:&#x20;

Send the query parameters with reference to the YAML file. The query parameters for the above api is attached in  Link for yaml:  [ ](https://github.com/Sunbird-cQube/spec-ms/blob/dev/spec.yaml)[<img src="https://lh6.googleusercontent.com/vz1PVdRSVzygs-DlegHLT1KDUWzJ5y6WDQD3V5CE-Szl9udxKtyL3yuPSqPy3tpkwN2UbYDE43uFQV-qzU1yjCeV6ESNlJD5xkmTSZds-4yEy3NWIt10Fs-D3UfRV6IZg-mNQD-HBg78jlreb_eY_q8" alt="" data-size="line">](https://github.com/Sunbird-cQube/spec-ms/blob/dev/spec.yaml)[spec-ms/spec.yaml at dev · Sunbird-cQube/spec-ms](https://github.com/Sunbird-cQube/spec-ms/blob/dev/spec.yaml)

Provide the valid input details for the parameters shown below.

&#x20;

<figure><img src="https://lh4.googleusercontent.com/A9aC5aKbdCDBsn6hFSiDRaxCxw54MaISIgJbFwoha5W71DmLuN6fN_8vb4JVpuUOus1tJsrk_rJ-_aPWYyWP7X2E3qVlXqXgaIWwmQZTbSiRgvAmox2a2ngdXWuXodOb2Pjgc2mtvweAq6xgSoHABrg" alt=""><figcaption></figcaption></figure>

### Step 3:&#x20;

Click on the send button for the request and if the request is successful the user should see a response message which contains the status of the file.

<figure><img src="https://lh3.googleusercontent.com/QMQPJtmMmhf6S0E1-d8BkO6Sx-VM3ST4l9C0XRTP4DPNGdytxOlaCSTT9GphsVj13-D-cnCOrjwdRJzj7rwV7pYyNTbQjenpNZiYlqcwxUsros6lqQrx-UiiOxyNuoSc9zRvXscjqb_t2HOT8iU9yqo" alt=""><figcaption></figcaption></figure>

If the csv files are too large in size, the upload process of those files will take more time which will make users wait for longer duration to receive the response from the API. As a result, the upload process will be running asynchronously and we have developed this api to know the status of the file at any particular time.
