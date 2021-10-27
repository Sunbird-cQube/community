# Admin Login Process

![Admin user flow through VPN](https://github.com/Sunbird-cQube/community/blob/master/.gitbook/assets/Admin%20Login%20Process.png)

Admin must follow  the 2 factor authentication process to perform the admin tasks. The Admin user should connect to the VPN to avail the 2 factor authentication by following the steps mentioned below:

* Admin has to secure the access OpenVPN access.
* Admin has to download the google authenticator app to his phone and register the app with the QR code showing in the OpenVPN Access server page.
* By providing the credentials & Google authenticator code to download the user-locked profile \(client.ovpn\) file.
* Admin has to install the client openvpn-connect application
* Admin has to create the OpenVPN profile from the client.ovpn file
* Admin has to validate the user authentication and Google authenticator code to login to the cQube VPN.
* With the successful authentication admin can access the cQube admin features by opening the local IP in the browser.

