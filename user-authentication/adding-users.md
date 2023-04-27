---
description: Explains how to add users to cQube V 5.0 via Keycloak
---

# Adding Users

There are 2 ways to add users to cQube V 5.0 via Keycloak:

1. [Adding individual users](adding-users.md#steps-to-create-an-user)
2. [Adding bulk users](adding-users.md#adding-bulk-users-to-the-key-cloak-realm)

## Steps to add an individual user <a href="#steps-to-create-an-user" id="steps-to-create-an-user"></a>

**Step 1 :** Post configuring Keycloak as explained [here](configuring-keycloak.md), navigate to the Users tab.

**Step 2 :** Click on the add User button.

<figure><img src="../.gitbook/assets/image (34) (1).png" alt=""><figcaption></figcaption></figure>

**Step 3 :** Enter the Username for the user being created and save.

<figure><img src="../.gitbook/assets/image (39).png" alt=""><figcaption></figcaption></figure>

**Step 4 :** Once the user is created, navigate to the Credentials tab and enter the required password, turn off the temporary password option and click on 'Set Password'.

<figure><img src="../.gitbook/assets/image (42).png" alt=""><figcaption></figcaption></figure>

✅ The required user has been added successfully!

## Steps to add bulk users <a href="#adding-bulk-users-to-the-key-cloak-realm" id="adding-bulk-users-to-the-key-cloak-realm"></a>

**Step 1 :** Navigate to 'Import' tab in the 'Manage' section.

<figure><img src="../.gitbook/assets/image (31) (1).png" alt=""><figcaption></figcaption></figure>

**Step 2 :** Click on 'Select file' and upload the .json file containing information of users to be added. (.json file should be in the format as shown below)

<figure><img src="../.gitbook/assets/image (37).png" alt=""><figcaption></figcaption></figure>

**Step 3 :** Post selecting the .json file, turn the import users option on. Then, in the dropdown, select 'Overwrite' if you wish to overwrite existing users with the same information or select 'Skip' if you want to skip them. If you select 'Fail', the process will fail in case there are users with duplicate information.

<figure><img src="../.gitbook/assets/image (45).png" alt=""><figcaption></figcaption></figure>

**Step 4 :** Post selecting the dropdown, click on 'Import'.

<figure><img src="../.gitbook/assets/image (32).png" alt=""><figcaption></figcaption></figure>

✅ The bulk users have been added successfully and will be able to login to the application using respective credentials!

\
