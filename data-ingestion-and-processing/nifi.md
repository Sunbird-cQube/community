# NiFi

Here we have different processor groups to process the data(Nifi canvas).\
1\. To run adapters.

2\. To run all programs.

3\. To run program wise.

<figure><img src="https://lh3.googleusercontent.com/1dm5Q1qDbwVHIVz6Si23o8u1pSYDqC2ObNtMp-XMVRSSW6xnel5SBWJpJ8AcHUNOwdvjFqg7PJ9Cu_XFoDKXFaARxpz7_usaYo9pW-k2-vGJHSQvLHKWyN0C__NsfDgifmEjqSzOcTMIXr2OuviryxI" alt=""><figcaption></figcaption></figure>

**1. To run adapters:** This processor group is used to run the adapters shell script code.

\


<figure><img src="https://lh4.googleusercontent.com/C0-b1HGD3LFThKZeTCivk2dVadzZ3KhbXVDZT4TLGLL41S1-yAmUF94sy0kav5ZRmK2hZEdFiO6L3zRAm_N8dgOJrfaScnaD_kH_VMf3pan_uPoIA-ywNgIRXR0kVVL-1fCqSZo6tBtarIE0S4zqaaE" alt=""><figcaption></figcaption></figure>

<figure><img src="https://lh5.googleusercontent.com/fpCjc1rpBYBnfONAoW9tGyTJyt0u05-P_T9jKexu2X_VoHjocEUKfz6Kzi2TA1Z1wHNDALXaiZUnJp9ypq90jVwRyinhFqJ6yjmWptbrmup_1DkeO4ytFph1w5EbFPW1JxY-14FQz_wWJKXA-b5MSGc" alt="" width="563"><figcaption></figcaption></figure>

**2. To run all programs:** This processor group is used to move files from process\_input folder to processing\_ms folder according to folder structures. .i.e., (dimensions/,programs/). Then it will run yarn cli ingest(where it will ingest all schemas and grammars to the database) and yarn cli ingest-data (where it will ingest all data files to the database) commands.&#x20;

<figure><img src="https://lh6.googleusercontent.com/iDJAihVlk5y_vojWc_FQjXwKzMysXI8gpgQ33O_Tn9zTwJ9xNXB03aZ4z3URQfU8SVG9Su3Fx6CDEOQMcyNpOjEsYScO9Q5Bbi8RFgwVECkl_Eir6QSYkcph0XREsrwBXirMQf-z4Z1UEhhF8zFkfeQ" alt=""><figcaption></figcaption></figure>

**3.To run program wise:** This processor group is used to move particular program files from process\_input folder to processing\_ms folder. Then it will run yarn cli ingest and yarn cli ingest-data --filter=’program\_name’.(where it will ingest particular program data files).

In order to automate these processor groups we have written REST-APIs.

<figure><img src="https://lh4.googleusercontent.com/Unv2sMXZDwQRXkk86yfrU2dlmHYh-owdrfeoEXydhOU2CooGAF--gVbO3xJjd2WJy4-Sh2HbLRgcOI1bqJrUElxDTdCtNuJUKPcUqdE28TqLjRQ5fsWKiaiwwWjEAxzL3pXzkyBo_A7N0eBXkoxsBlo" alt=""><figcaption></figcaption></figure>

[Nifi-Rest-api’s code](https://github.com/Sunbird-cQube/generator-ms/blob/dev/static\_processor\_group/add\_nifi\_template.py)
