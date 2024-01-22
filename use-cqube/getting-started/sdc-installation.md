# SDC Installation

**Step 1:** Use the following command to connect to the On-premise instance

&#x20;     **ssh -i \<path\_to\_the\_pem\_file> \<user\_name>@\<public\_ip\_of\_the\_instance>**

&#x20;      **Ex: ssh -i poc\_key.pem -o ServerAliveInterval=60 ubuntu@13.200.12.31**&#x20;

**Step 2:** Clone the cqube-devops repository using following command

&#x20;        **git clone** [**https://github.com/Sunbird-cQube/cqube-devops.git**](https://github.com/Sunbird-cQube/cqube-devops.git)    &#x20;

<figure><img src="https://lh4.googleusercontent.com/LVrcmhInvNGnFXBZ2ZRHWZMqBGRqCX9DKsXteWhbRmV6X6EPDDo7TDOnwyDKjgahfIVWnnqsrXZ31AXnc5HOpDgcZEKdaBQN64bli_8wbM4xHZxmICUKdKIsXIkfqYGiXvE70Ryxtvnv0sttt0KbQnQ" alt=""><figcaption></figcaption></figure>

**Step 3:** Navigate to the directory where cqube is cloned or downloaded and checkout to the desired branch(Release Branch)

&#x20;                  **cd cqube-devops/**&#x20;

&#x20;                    **git checkout release-v5.0.5(latest release branch)**

<figure><img src="https://lh4.googleusercontent.com/qGnkWolEPHARu8cx0EFfpfyErug71YUFL6BzcboIVFdeKbZcrnnGtPJX3K4bRWTOJ9z3_LqR7LG5UWaVd3FkBcAuQA4Op8v_SW7DhsKL3Mk06TrIHX3zR0hRfgUTOKqUtSag5H01zkoK7kTIRMJ-ZPo" alt=""><figcaption></figcaption></figure>

**Step 4:** Give the following permissions to the install.sh file

&#x20;                 **sudo chmod u+x install.sh**

**Step 5**: Install cqube with non root user with sudo privileges

&#x20;                **sudo ./install.sh**

<figure><img src="https://lh3.googleusercontent.com/8-TCjndfNmhcIz0VcBUThl0Tt7D0eabbgLg6BFNZBLP1PDysbYUIjQXbkE7S2COFUfCg-qrD7MkZIzGITkzEQcYrzqSmrHudpWKKLFU62AdAKOiP_of_DII9H4keBrEZKyRYY-ihPNf2KA1Dcmm-d_Y" alt=""><figcaption></figcaption></figure>

Install.sh file contains a shell script where it will run shell scripts and ansible-playbook to setup the cQube

**Step 6:** User Input Variables - These are the variables which need to be entered by the user by following the Hint provided

* state\_name ( Enter the required state code by referring to the state list provided )
* api\_end\_point ( Enter the url in which cqube to be configured )
* Storage\_type : Local
* Mode\_of\_installation:Public

<figure><img src="https://lh4.googleusercontent.com/d58hbAaNpvDKOPouLI5bvLkM-2ZrqiKBsHOT5tXqVWta_lcI45p4QJ0UkdTv416tGw9VBTqz1GoIFgXqe8W4QJ2UetHRmhwbD0NmJfhIuu02TwC7ek-4VFx_0-SKcn7xlgR7syoWuoAGKDPq90PhV7c" alt=""><figcaption></figcaption></figure>

**Step 7:** Optional\_variables- Database credentials contain default values. If the user wishes to enter their own credentials then the user should opt for yes to enter their credentials otherwise can opt for no when the question pops up

* db\_user\_name ( Enter the postgres database username )&#x20;
* db\_name ( Enter the postgres database name )
* db\_password ( Enter the postgres password )

![](https://lh5.googleusercontent.com/PQSTfzWT0BPjtTe72EuCIiDxpO10S6XPn7Mv66t30yyuerrjWb4B9oUMtojPUjyeAwakZgOxQLpnY0VkHJN4i1g7BOWjYBh3C5EZXafu16YSZtbdUnTfh4mbdpCna0JuWBpbVPJUUU\_Y\_dtL6Bf6xUY)

**Step 8:** Once the config file is generated, A preview of the config file is displayed followed by a question where the user gets an option to re enter the configuration values on choosing yes. If option no is selected then the install.sh moves to the next section.

<figure><img src="https://lh4.googleusercontent.com/xIyf4G-HwzWAB0L9y-sFwH1s7jfXnoQB9G0oSRbVjlUNvzLh2QdlKY9W6dgeKcRocoL4koqk1nLBEwU7OGQV4ui1mpK6_l-9xDtk85UuL6Md6cRmiogUjfeJW02FF5abNuKvUwYqSLydl7uVeFXgXa0" alt=""><figcaption></figcaption></figure>

**Step 9:**  A preview of the program\_selector.yml file is displayed followed by a question where the user gets an option to enable or disable the programs on choosing yes. If option no is selected then the install.sh moves to the next section.

<figure><img src="https://lh5.googleusercontent.com/84BynE9o-c4gHYwC5w_2GjkzCI1KxO1IrgVCK5cz_x6px4cweNM5kpFvGk9NC2Hca1lXUh9lmiedor9d8uCs6Np9VDAIPhOcU6bet29Cd6aCjh_jNNU7P9_aAOcAUcHV8Ua9rmrcwSuGF065hW6Ei2U" alt=""><figcaption></figcaption></figure>

**Step 10:** Once the installation is completed, You will be prompted with the following messages and required reference urls.

&#x20;              **cQube Installed Successfully**

**(Note: The installation process is expected to take approximately 30-40 minutes.)**

cQube ingestion api can be accessible using \<domain\_name>

<figure><img src="https://lh4.googleusercontent.com/1u8Ey9_9IWWC4yycnYp1T5jrekIJxNIxy9yrvlx4vChVHIvHa97W1Em_dKuLb4yN9pQfA_Rd77oBO1HoEdq171JY7EoByfA2kESaifZG5dPtA_bgTHkcatjSiPp9lvruGSDrpVHBCzrm_FrlzPw3N4U" alt=""><figcaption></figcaption></figure>

\
