# Public/Private dashboards

During the installation, based on the inputs of the installer, access to the access for the program will be set to either public or private.

Public Access indicates that the program can be accessed via a public dashboard with a login as a user.

Private Access indicates that the program can be accessed only via a private dashboard, which is once any private or admin user is logged in.

Keycloak Admin can override the access from the keycloak admin console by following the below steps.

1. Navigate to the roles tab. Select whichever role admin wants to modify the program access to.

<figure><img src="https://lh6.googleusercontent.com/nxeAOQ03qRS2oGlD3YgiFbDPsQfutto5Cug0wASsbWKTO_icgZoMogZKdZ-DRLZSC4G_XtEKxtHqQ4jNcJFipjFpQ4VBpU_IhK52KwjqkuolDoc41DQugs22NbbHnscKgvC9dfaq86sVhjaFUUeBkQQ" alt=""><figcaption></figcaption></figure>

2. Once on the selected role page, select the attributes tab.

<figure><img src="https://lh6.googleusercontent.com/nxeAOQ03qRS2oGlD3YgiFbDPsQfutto5Cug0wASsbWKTO_icgZoMogZKdZ-DRLZSC4G_XtEKxtHqQ4jNcJFipjFpQ4VBpU_IhK52KwjqkuolDoc41DQugs22NbbHnscKgvC9dfaq86sVhjaFUUeBkQQ" alt=""><figcaption></figcaption></figure>

3. Modify the value of the attribute named key, which is a string consisting of comma separated program Ids and save to apply the changes.

<figure><img src="https://lh4.googleusercontent.com/KjOot73rZdxGmYJhtVVVVSXhm9vaBgTMKHLAg2SnhJLJSQAPGixhNgKEwH0Li4B8tlNOXBylN95_3bE9R4YUmwK0na02N9nk_twQE0ntcVObHmAPlO3NMMEAiY1Qkw1PlwPtUw12c4r_5Fu0XewQsdw" alt=""><figcaption></figcaption></figure>

4. Any role to be added can be appended to that string with a comma between each programId, or any program ID removed will no longer be accessible to the selected role.
5. Currently configured Program ID’s can be found in a table of spec schema: **spec.DatasetGrammar.**

Also following are the IDs that are currently available and configured program IDs within cQube:

&#x20;

* nishtha
* pm\_poshan
* nas
* diksha
* pgi
* udise
* sch\_att
* nipun\_bharat
* ncert\_quiz
* micro\_improvements
* telemetry
