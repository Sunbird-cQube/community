# Changing Program Name, Icon and Side Menu Sequence

The name of the programs, icons and sequence of the side menubar can be changed as explained below.

<figure><img src="https://lh3.googleusercontent.com/iipFUbCzEi05qxyMu_gEtR-dGWuKURVMOuTHZKZG84wq4Gzj0EafQ5OsYrHOmYMGAx14bg2mffe7ae4XBn2ZrmS7jkjtvy8hreKtina4e7FafJMwd7gzqvryst4iA6iWolas-No52E-4GpRBxPrP-es" alt=""><figcaption></figcaption></figure>

This can be changed in the menu configuration file present in the query-builder micro service (query-builder > menus.csv).

<figure><img src="https://lh6.googleusercontent.com/L0u8bVkegAyF0vMcPltdTQBdZX8qQVMPAtEwWvvz9MmXHA-8Kh0Yndpgj1PbjxlgWr31-_OgHcdJbUo5KUH-qZ80ySGSJp1etiW0g_G1Emr0FyyHQglD8z0gbYiREHsD7XG8583PlgIbnclG510YURY" alt=""><figcaption></figcaption></figure>

The users can change the menu sequence and program name in this file. They need to add the required details mentioned in the CSV to add a new program in the menu bar. If they add / change any icon for the menu, they need to upload the icon images into the following directory dashboard-ms > src > assets > images

The sample CSV filled is shown below:

<figure><img src="https://lh4.googleusercontent.com/FUKQ_lmnIovRIrBVem4okG00Ws_5RlDSBVIWA4L5TqhVmAWUq12DKY6HCue_H7mhtJsUULfvQVmXR2CWRyrOGm7xU2RkErxkl2zMBk-gp3HEfYmhl19RLH4D45D0MxMoRzIRy8N9HuVaV6G3RGM_q4k" alt=""><figcaption></figcaption></figure>

Post making the changes, the user needs to redeploy the code again as explained below.

### Steps for redeploying cQube UI post changes

Run the commands below in the given order to redeploy the menus.csv file changes for them to be reflected in the visualization layer:

`sudo docker stop querybuilder_app`

`sudo docker rm querybuilder_app`

`sudo docker querybuilder_ms:1`

`cd cqube-devops/microservices/querybuilder-ms`

`sudo git pull`

`sudo docker build -t querybuilder_ms:1`

`sudo docker run -d -p 3002:3002 --network cqube_net --name querybuilder_app querybuilder_ms:1`

\
\
