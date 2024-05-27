Applying this manifest will start Ubuntu Linux 22.04 LTS (Jammy Jellyfish) - running the OpenSSH server and the **GridFactory** batch service.

By providing a public SSH key you can access your container via SSH.

The image will pull your X.509 key and certificate from ScienceData. For this to work, you _must_ tick off `Allow internal HTTP access from your own pods` and click `Generate new personal X.509 certificate` in your [ScienceData settings/preferences](https://sciencedata.dk/index.php/settings/personal#panel-userapps).

The image is pulled from our Docker registry. Build recipes are available on [GitHub](https://github.com/deic-dk/sciencedata_images).
