---
description: >-
  Below are the steps to copy SSL certificates from a local source to Ubuntu and
  from Windows to Ubuntu.
---

# Copying SSL Certificate

**From Local to Ubuntu:**

1. Please find the below command  to copying ssl keys from local ubuntu to ubuntu server&#x20;

&#x20;               sudo scp -i poc\_key.pem \<Name of the SSL keys > ubuntu@\<IP>:\~/

2. After copying the files from local to server then we need to move the SSL keys (.crt and.key) to the mentioned path.

&#x20;              Path: cqube-devops/ansible/ssl\_certificates

&#x20;              cp \<ssl certificates> /home/ubuntu/cqube-devops/ansible/ssl\_certificates

**From Windows to Ubuntu:**

1. Please find the below link  to copying ssl keys from windows machine to ubuntu server(winscp,filezilla)

&#x20;             [https://www.hostgator.com/help/article/how-to-transfer-files-with-winscp](https://www.hostgator.com/help/article/how-to-transfer-files-with-winscp)

2. After copying the files from windows to server then we need to move the SSL keys (.crt and.key) to the mentioned path.

&#x20;            Path: cqube-devops/ansible/ssl\_certificates

&#x20;             cp \<ssl certificates> /home/ubuntu/cqube-devops/ansible/ssl\_certificates
