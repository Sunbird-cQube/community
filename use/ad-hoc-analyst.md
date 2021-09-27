# Ad-hoc analyst

* They are the dynamic report creators of cQube. 
* The ad hoc analyst can make use of third-party visualization tools like METABASE, Tableau, KNIME or any other visualization tool to create dynamic dashboards and develop dynamic reports by directly accessing the database in read only mode using OpenVPN.
* Ad-hoc users can download the JSON files from the S3 output bucket through the API.
* The example spec for the download API will be as like below

API headers 

```text
{
   "Authorization":"Bearer access_token",
   "Content-Type":"application/json"
}
```

**List S3 Buckets API Endpoint**

**GET**  https://cqube\_domain/data/list\_s3\_buckets 

Output Body

```text
{
   "input":"cqube-input-bucket",
   "output":"cqube-output-bucket",
   "emission":"cqube-emission-bucket"
}
```

**POST** https://cqube\_domain/data/list\_s3\_files 

Request Body: 

```text
{
   "bucket":"cqube-output-bucket"
}
```

**POST** https://cqube\_domain/data/download\_uri 

Output Body: 

```text
{
   "filename":"school_master/2020/2020-06/2020-06-04_school_master/04-06-2020_13:12:59.574_5e1 60862-c5b3-4121-9a96-ecefa34fc264_school_mst.zip",
   "bucket":"cqube-gj-input"
}
```

