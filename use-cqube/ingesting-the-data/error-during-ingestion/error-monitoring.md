# Error Monitoring

The error file captures all error records during the ingestion process and is uploaded to the relevant cloud storage. Users can log in to the respective cloud storage platform, navigate to the designated bucket created during installation, and follow these steps to access the error file:

1. For the new\_program API: a) Error files are stored in the "ingestion\_error" folder within the bucket. b) Within "ingestion\_error," there are folders for each program (named after the program\_name). Inside these program folders, there is a sub-folder with the current date as its name. c) Users can access the current date folder, review the error files within, and download them to examine CSV errors.
2. For the national\_programs API: a) Error files are stored in the "emission\_error" folder within the bucket. b) Inside "emission\_error," a folder is created with today's date, containing the error files.

After identifying and rectifying errors, users should re-upload the entire file. Screenshots illustrating how to access error files are provided below for reference.

<figure><img src="https://lh7-us.googleusercontent.com/QnTX6IoTuCGCcumCKqS0KuItQNSv2bQO3PbP9785jzP5oS62D6hTyXEGvK_nfoT7R22IAlKJ2fcm9QvhpuvmZ6fUubdZ8U4fq7gm-kX2qfkBSaOlT4O_jpvWR1gJQzJVpA4AvoXwlyadpvMhD0P-P0Q" alt=""><figcaption></figcaption></figure>

<figure><img src="https://lh7-us.googleusercontent.com/8jmipM9DFgiXIVMBDAtuqwzAvCI1Jv0Siw33vk_Xph11PAYuz3DmAXZGz7340s9DQrTalis5RF-c0xIgji3frDmO3zCVB_G2qb4JfwSaoTw397D4A3mNQiLS54ySCNCwu88FA22VbFSy-h5bjtSuRGM" alt=""><figcaption></figcaption></figure>

<figure><img src="https://lh7-us.googleusercontent.com/mG-FJpanjok4LQIj4QzXVI8vgmcpmKfvVG09bgcdD8_nvCE5CG2GDbkkNrhSU14cr6aYxbuS5XOyBpMRk2G4NM3gOChuuIYZJm54ydzvCsrg-HH-Sh-vwBPARbANme-2SKEfzoOjVyKfz5e49NGh70Q" alt=""><figcaption></figcaption></figure>

To get the count of processed records and error records GET /ingestion/file-status API can be used.

\
