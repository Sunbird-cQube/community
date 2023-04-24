---
description: Describes the steps to configure Keycloak as a service for user authentication
---

# Configuring Keycloak

Following are the steps to configure Keycloak post installing cQube V 5.0:

**Step 1 :** In a browser, open \<domain>/auth and go to Administration Console.

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

**Step 2 :** Enter the keycloak admin username and password that is set as part of the cQube installation.

<figure><img src="../.gitbook/assets/image (35).png" alt=""><figcaption></figcaption></figure>

**Step 3 :** Navigate to the Clients Tab of the **cQube** Realm and select the client (**cqube 5.0**) created during installation.

<figure><img src="../.gitbook/assets/image (40).png" alt=""><figcaption></figcaption></figure>

**Step 4 :** Fill the valid Redirect URIs with the domain of the application followed by ‘/\*’

**Step 5 :** Fill the Web Origins with the domain of the application

**Step 6 :** Turn on the Direct Access Grant Enabled and save the changes.

<figure><img src="../.gitbook/assets/image (38).png" alt=""><figcaption></figcaption></figure>

✅ You have successfully configured Keycloak for user authentication!
