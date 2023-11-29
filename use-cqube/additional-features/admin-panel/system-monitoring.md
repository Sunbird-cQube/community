# System Monitoring

System monitoring contains information about the system resource consumption and status about docker container services of cQube.

*   Once the user is logged in to the admin panel. Click on monitoring, It redirects to another window where you will be able to see the grafana dashboard.



    <figure><img src="https://lh7-us.googleusercontent.com/sFQuePVF4oaTVHt-8yW6KZYnrNMbcEGxC7oppHV5fHQOiWFlBqr915cpUDJJYCiCVKE-wx9S5Ve6Axi3D379iCJL0Lood8qdQkdee3tKNpu3GTBS0JMM1s5FVrEcVadwRmC-gddQPYonATluOyqz0_0" alt=""><figcaption></figcaption></figure>



    * By default the username and password will be the following

    Username: admin

    Password: admin

    * Click on login and the change the password as prompted



    <figure><img src="https://lh7-us.googleusercontent.com/d1UfOGVO4a37D8dedJe8gynFbYOIhtqvyRoyZE9xRLD5yajiLKUAPOvDWFlsWNJCpM6BHpBApb4s8zHOsK9Eh9utZPsd6_OoamzZToLErMW5zJAPF5caeYSJqoEyUeGsKvYfAZJHNkoYLgfyebY6ev0" alt=""><figcaption></figcaption></figure>



    * Login to the grafana dashboard and click on the Toggle Menu bar and then click on Dashboard



    <figure><img src="https://lh7-us.googleusercontent.com/t33P6WCZRf_SCu7uogWqU-PlPyhQca2oHcm3_BMCa1txBJ9U_rl224Ryx5_ZZw2vo7yDqnFQ-g2K4mZWcLk3PE9R4-ViSFvftYt9P-YIQEJ9vy1FLw6ooZ6ubnPDeqeCLZ52OnvCjx_HM5Wx2bmKryM" alt=""><figcaption></figcaption></figure>



    * Once you click on dashboards, you will be able to see the dashboards. Click on General to expand the dashboard.



    <figure><img src="https://lh7-us.googleusercontent.com/4p-PqLW2NHqXecScpPJ--bLB4TNn1KvJBW2hy306o1-fdrzzFbYG0NemIWTdgQ01xzPJWZ1WfnYwJg13TWithGDWgIty0m0pDeloEHgXv-ZHSysEXUJYinsOesG4k7bFsLVTkvsf4jEL5jSv86yV5rc" alt=""><figcaption></figcaption></figure>



    * **Docker containers:** This dashboard contains the general statistics about the docker container performances.



    <figure><img src="https://lh7-us.googleusercontent.com/jMHu30TEmvttPBS9uWtvgigFj3A-N-kgLEdvg7UnJUxBzDpeOO12DBwH4y_cNx4werMBQramPqlKCJWbEEAh7xi3nwaXI2aEoQM7UdcHCYNqANMvqz3mwyhsjGe29MDMT0XCAhYBVFs1YLCAy4hCcEI" alt=""><figcaption></figcaption></figure>

    CPU used: This module gives you the total number of CPU used by the containers

    CPU cores: This module gives the information about the number of cpu cores the VM is running on

    Memory Load: It gives the total percentage of memory load by the docker containers

    Used Memory: It gives the information about the total GB of memory in use by the docker containers

    Storage Load: It gives the total percentage of storage load by the docker containers

    Used Storage: It gives the information about the total GB of storage in use by the docker containers

    Running Containers: It shows the total number of containers which are up and running

    Container CPU Usage: It shows the usage of CPU consumed by each container

    Container Memory Usage: It shows the usage of memory consumed by each container
*   Infra Metrics: This dashboard contains the general statistics about the docker infrastructure

    \


    <figure><img src="https://lh7-us.googleusercontent.com/RRKwLw1QrTck2vk2jwRkqhCur0I-mnSF69bMUDKuEM9sm0UapStB5vfbutwRyCoWzgd2R2VTI1GfKP7uaxmver98ZMUxGVo7UpE8AMKTATM-sP_YKzxuCo-OiqIelOIXQUiX0GN_SyxRy0ryz03YOjc" alt=""><figcaption></figcaption></figure>

    Uptime: It shows the total uptime of the server from the last shutdown.

    CPU idle: It shows the percentage of CPU idle at that particular time

    CPU cores: It shows the number of cpu cores the VM is running on

    Available Memory: It shows the total GB of free RAM in the VM

    Free Storage: It shows the total number of free storage available

    CPU Usage: It shows the usage cycle of cpu

    Memory Usage: It shows the usage cycle of RAM

    Network Usage: It shows the usage of input/output network usage
*   **Monitor Services:** This dashboard contains the statistics about the monitoring services.

    \


    <figure><img src="https://lh7-us.googleusercontent.com/zbg2NLQJoUncVF36YAH5hHnEecKmzLGm76Geva6kmbJgR8hF-JUedt2WnPLCexDx11Xi2fDP_zTzrgEPq3xpdDHrL8RZwi5_ui532bumUzaKWUMCFv-V_0RgWlvYTAKRXU-b29gw7-TFgiv2dPuI7w0" alt=""><figcaption></figcaption></figure>

    Prometheus uptime: It shows the number of minutes prometheus is up and running

    Memory Usage: It shows the memory usage of monitoring containers

    Container CPU usage: It shows the percentage of cpu used by monitoring containers

    Container memory usage: It shows the percentage of memory used by monitoring containers.&#x20;

    \
