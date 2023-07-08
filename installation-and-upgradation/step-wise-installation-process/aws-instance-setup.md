# AWS Instance Setup

**Instance Setup in AWS:**

* Create an EC2 instance with Ubuntu 20.04 to 22.04, 16GB RAM, 4 core CPU, and 250GB HDD.
* Configure security group rules to allow inbound traffic on ports 80, 443, 8000, and 5432.

**Kong Configuration:**

* Configure Kong to route ports 3000, 3001,3002, and 3003 to the respective cQube APIs. (Already configured in one step deployment)

**IAM User and Role Creation:**

* Create an IAM user with administrator permissions and obtain the access key and secret key.
* Create an IAM role with S3 access permissions and assign it to the IAM user.

**S3 Bucket Setup:**

* Create one s3 bucket
