# Adding  an individual user

**Step 1 :** Post configuring Keycloak as explained here, navigate to the Users tab.

**Step 2 :** Click on the add User button.

<figure><img src="https://lh6.googleusercontent.com/9_gt-INUgN3uRi38bpffr2NG-zGSzJUutgjzE24oZCWPEit-ItlIOPQupVxXrkqkKnPZEYoZIZmGs8sEThlnLKcQx-frhFe9QQwOmwSUBW7keBvYJ06xY62GRiIRXSF7_4Sp7CdKv4r9YNe8d3-h-lk" alt=""><figcaption></figcaption></figure>

**Step 3 :** Enter the username for the user being created and save.

\


<figure><img src="https://lh4.googleusercontent.com/jxokXbfNzN7GM-GKJfff10w3nWc-F8gCuhnay5YI7-t6P0vO3xsf6jSNfzPmEOh8cK2vZl3oPt_1tsz-ZY86yC2ET0ldegayY2fbMQZq0hj6bwo_9Q6DMZAkEljZg8Wf-gbrpY8iCkNUWDY8SBkjA9o" alt=""><figcaption></figcaption></figure>

**Step 4 :** Once the user is created, navigate to the Credentials tab and enter the required password. Turn off the temporary password option and click on 'Set Password'.

<figure><img src="https://lh6.googleusercontent.com/FTObnD0Tike047IKtWyf1pb7JKbjyf6u0v3xaQRPTeZPZKGuN-msk5VNcUskJ2hNi-99C2Ws-fJyuxSE77k4zzZsl9DOxz1RkXb144Ndqf98zwizx2KZAXIoxnI_4aWaHgJ0L5HBgRBsjr7-akrPazk" alt=""><figcaption></figcaption></figure>

Step 5: Navigate to the Role-Mapping, under Realm-roles select private\_user and click on ‘Add selected’ button. This will assign the private\_user role to the created user.

\


<figure><img src="https://lh6.googleusercontent.com/WU7R49zl1M-KKoO1AK17BbzUU_uVcBrOYeBzbwz_TKWo8R9xuYzvX6EdnRfCtZk3p3HION3sJmkwAaCh0ziaqVMdVhAjVdTEdPHOa5xF5KpkVd-1KsSxO3d9Sj4Icn_nbXv8KPwx9I1ei5VY1FiKkBo" alt=""><figcaption></figcaption></figure>

✅ The required user has been added successfully!

**Steps to manually enable the flag to store Role-Info**

**Step 1 :** Navigate client scopes on the left hand navigation.&#x20;

**Step 2 :** Select roles under the client scopes in the table.

\


<figure><img src="https://lh5.googleusercontent.com/w9NGiRzpF2-7yBjdSjh_8vNp8MhpHBIk2T7QQ4BEfBaWKxNbWWapNEKo-6I9bhc1ZpY-6rlWevKna3RInTbHYj3Jk3Da4i3j7g8q7_-2LS9yDA4ExzhPDAydmCoS_ioJBWRwbl-fs6l2s1f7ZUu7gC8" alt=""><figcaption></figcaption></figure>

**Step 3 :** Navigate to the Mappers tab on the top and select realm roles.

\


<figure><img src="https://lh4.googleusercontent.com/yYgd2l533KKBJQyHDUjr3gqIw3vVu6Fs0TIgHfU1KqKWWKpiLVSammtnNYTMr_L8XAtCiLQTYho2rok9mrdSOd11u6VOmpLQpVdSivShYl48sPU1jlxwO5DDsoSlHcPIvchfJDkIvSKBpXHv3fOXT-E" alt=""><figcaption></figcaption></figure>

**Step 4 :** Toggle Add to UserInfo button and save.

\


<figure><img src="https://lh5.googleusercontent.com/UbFCVNB98nQSJ1I2zx-wBsP1ZX-zaqrWZ8S7vXVN5QcQqXT49ibn6rSHVjrZB2zlmFoW1QuRqYnUgDMq_1pf9PY0QKokIsZx1z1Nw7kxapBKEvyIGzo-V8lK37Js8jgDZ8x5QGb6qBmNJkqgNfRv-hM" alt=""><figcaption></figcaption></figure>

\


#### &#x20;bulk users

Step 1 : Navigate to 'Import' tab in the 'Manage' section.

<figure><img src="https://lh5.googleusercontent.com/JnzuT_4qD3rnHXoehyc1yq7QA0txxC-81ph_6cW88TkaqzRdr0UOhinM87FYSqXOBUIoY-SqBYx2q5D_PtqmYJPJJSuMZhMTPlnbyVnre1PZdftA17011MS0qKRF6qp4mF3QgZohk2PDvsGCQlfbjSU" alt=""><figcaption></figcaption></figure>

Step 2 : Click on 'Select file' and upload the .json file containing information of users to be added. (.json file should be in the format as shown below)

\


\
\
\
\
