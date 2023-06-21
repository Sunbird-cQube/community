# Error monitoring

The error file will store all the error records during the ingestion process and will be uploaded to the appropriate cloud storage. The user can login to the respective cloud storage and download the file to take a look at the error records present in the csv. The below mentioned steps will specify on how to access the error file.

1. The cloud storage bucket/container will be named as cQube-edu.
2. Inside the bucket there will be multiple folders for different processing stages and the ingestion error files will be stored in ingestion\_error folder. This folder will in turn contain folders for each program, the name of the folder will be same as the \<program\_name>.
3. The \<program\_name> folder will internally have a folder which will have current date as the name.
4. The user can access the current date folder if its present and can see the error files present in it and download the error files to view the errors present in the csv.

Please refer to the below screenshots of different storage type( Minio, Azure and AWS) on how to access the error files

Accessing error files in Minio Storage

<figure><img src="https://lh4.googleusercontent.com/1pqgvbGh5yWlbTQNE0Xpi5wloBi_c1CPUo-lDC_uaUsNerNGb9rmkIHdKhY14HGPrdjsgs22DMxGiyCa6Lbb__IPyXjxg1z4w6doHLAo23L4Fj36Qap4esj_c_-nnlcAU9o4H0YU9iFBrgdQFHAcEbE" alt=""><figcaption></figcaption></figure>

<figure><img src="https://lh4.googleusercontent.com/n_cCpfnmg1kr-hvXXCwj5LjsBsy3RNdbOH1bK2wNe1Zakatns8bQlCndbIt1DYrUEiT02F9sUN27AhoU8rnt3w31PiXLW3R0xhNy1yeVkAqAP1oBp09upStw3SLEJv8wl2D4eH5KdHhi-a2xJvtIwhs" alt=""><figcaption></figcaption></figure>

<figure><img src="https://lh5.googleusercontent.com/SVbRXh-Og-XroErf1CME0r2arM4B1-zmgcxtcpFTq9_COImLNUiPOwa8-bAHdLtV8yEtZmGKWNHUW62gHqvlNNjIwNprMyaNosrhoTtcoikqxCNaIiH1bYAPIUcBXbtWUHyD1rvenlX_9-xOvqRRS5Q" alt=""><figcaption></figcaption></figure>

<figure><img src="https://lh4.googleusercontent.com/C_5-bgmiaVedzMOm2URfhIN5JHoKvkef0m5949FrCA_h7jIjYfL-sQfaXyq3DaaugmhdpViLaR2lZ13SkIZ_v1SdN-zcoIc4z3Amo4b82ygEo7Zaqx9UrtCbMQ8F9_D_lglj7XramkqePo2Edk0bzj8" alt=""><figcaption></figcaption></figure>

### **Accessing error files in Azure**

<figure><img src="https://lh5.googleusercontent.com/2NmyxVq2mV21AE2mTWk0QsfuP-QtH7_BZH0VPPl2hFZGx5nQNIRXuuhcVxHH6HF0jni03LfIhaMJiXI3VohypHMfDiUlTbQxL7foxuPAc0LaxNux6N5tnb3M3IDAlRU0blkg2TR9XoQJo8Jm273czhE" alt=""><figcaption></figcaption></figure>

<figure><img src="https://lh6.googleusercontent.com/6poYzGTTN_j0tu9S_vwfgDPjldvhkEht6hvuflkh247jbYBcSPbWv7t2tiJbdJpmLK11Ipux37egv8N1jLi6Bgmp-Mr-sfbDlyVBZOCaIetdjXl1UVKN5-tmPcTGRviCbcsHNAhEOvedvgtsUw_IbWE" alt=""><figcaption></figcaption></figure>

<figure><img src="https://lh4.googleusercontent.com/MS8asUejykXF6XxgLXgBpeFWJ-NEiewhxpHv0Opcq0K3U6JFJ4J7dGoOHe8siUtubBt5dg-X09m9CJnhas1gXieb5PzCWpnE_GyRtyCDP61uL3TxT-p1w378Fzbd7ughs3drSJDpy75Bpd2JRY8-5lU" alt=""><figcaption></figcaption></figure>

<figure><img src="https://lh4.googleusercontent.com/5g2e1dgCzDSaZd214dQYrWjyo8J4cZxsT4gaUrS03QKQtEV-KS1NFrsQdijs1uImDM3zviXqCrMj7YKpj36tI-dqsyXUb6J-AQCmxjdwi2mWN-vFLeBivJBy7_85rEchNtfLULg-fBBsB5Kqs9uzTYU" alt=""><figcaption></figcaption></figure>

### Accessing error files in AWS

<figure><img src="https://lh6.googleusercontent.com/I656QpbrUsj1mrh1kYpkCAUXRLgyVj1brimCrz1w7FcqFuTYyDzb47lo5IGU8Bs3z_SpRH7T1BexoF0WPRhxmUqMtZ8M7FEu8l5jCAbzJMM87rPFianXaJAGqZ0kz5TUwZW6sMpwDS8UT7wZfdCHbpg" alt=""><figcaption></figcaption></figure>

<figure><img src="https://lh6.googleusercontent.com/Ib6rk5dDHpsJAlYldGNjr3fbBBuD6ReEwC2-2Yk4RSqDOk6PLtmyzl7f6bSp8cHNRqVAgCNE9sa8G1zizT4dzvEu41ordAFuLiJDHgGhMsDSjRJjfoPPtqZiYOoZmoJU9BPUliXN0WdqNUjLO5fe7Y8" alt=""><figcaption></figcaption></figure>

<figure><img src="https://lh6.googleusercontent.com/OFjhT6O7nNjfaKh5DU4HeY4wlNgwM00A0gtz3vD1Qsy7178-Bp1FhsYYgcBN4Q10yVpzRkJHgho1RtmVQR1O8gjOI_Mg2viMe8_Zxew4k0fwNKGtIQSTsTnulRdfhcC5ZRH9qOAkrkDi3bMKqahEbDU" alt=""><figcaption></figcaption></figure>

<figure><img src="https://lh3.googleusercontent.com/dWLKI4zz-pBUgkv98TwJAPwQ7QAGJUJKETfHHWLbjSBShM892vColZz-nqdD30lxmanPVLLj2FuemtqIRRNd6N2wSU-BowKURbLmTyORvU7tYXa6ZQrtVwN_JdqzWZRhZKWA0If-swRsliNxRBOsZrc" alt=""><figcaption></figcaption></figure>

To get the count of processed records and error records GET /ingestion/file-status API can be used.
