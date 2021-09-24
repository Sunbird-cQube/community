# Angular & Node Issues



|  | **Where** |  | **Why** | **How to resolve** |
| :--- | :--- | :--- | :--- | :--- |
| **Error message** | **Error Location** | **Error type** | **Error identification \(Cause\)** | **Probable resolution** |
| Internal error. Please try again!! | On Browser | Exception | Issue in data, key not found, or file not there in s3 | "1. Make sure the file is available in s3 or not  2. Check the data format is correct or not." |
| NoSuchKey: The specified key does not exist | /opt/cqube/logs/server\_side-error.log | File not present exception | If specified file is not present at its location | Make sure all file are available which we are used |
| Request failed with status code 401 | On Browser | Unauthorised user | When ever token expired, user will be unauthorised | User should refresh page and login with valid username and password |
| Error: uncaughtException: ENOENT: no such file or directory | /opt/cqube/logs/server\_side-error.log | Local file is not there at given location | The file which we are trying to read is  not present at its location | We should put the required file at given location |
| Error: Request failed with status code 502 | On Browser | Bad gateway | If specified url is not accessible | Restart the ngnix server or otherwise give sudo pm2 resurrect |
| UncaughtException: The specified bucket does not exist | /opt/cqube/logs/admin\_server\_side-error.log | S3 bucket not exist | The bucket which we are trying to access is not present | Create all the required buckets |
| TypeError: Cannot read property 'toString' of undefined | /opt/cqube/logs/server\_side-error.log | Key unavailable | If specific key is not found | Make sure key is there in data, if not there put it as empty or null value |
| TypeError: districtData.map is not a function | /opt/cqube/logs/server\_side-error.log | If file has no data | If file is there but data is null | If data is not there don't create files |
| NetworkingError: socket hang up | /opt/cqube/logs/server\_side-error.log | Network issue | If network is very weak or not connected | Check you internet connection |
| Error: Cannot find module 's3-append'/any | /opt/cqube/logs/server\_side-error.log | Library not installed | If we are using some module that is not installed | Do npm install and rerun the server |
| TypeError: Cannot read property 'keyname\(any key\)' of null/undefined | /opt/cqube/logs/server\_side-error.log | Key unavailable | Trying to access a key which is null/undefined | Check the data,  if key not present put the key with null value in s3 files |
| TypeError: districtsData.sort is not a function | /opt/cqube/logs/server\_side-error.log | If file has no data | If file is there but data is null | If data is not there don't create files |
| RequestTimeTooSkewed: The difference between the request time and the current time is too large | /opt/cqube/logs/server\_side-error.log | System time not correct | If syatem time is different from actual time | Change your system time to actual time |

