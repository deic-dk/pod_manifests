Applying this manifest will start Ubuntu Linux 22.04 LTS (Jammy Jellyfish) - running the OpenSSH server and a batch worker daemon (GridWorker), which will pull jobs from the list of **GridFactory**  batch servers configured in the 'Peers' text field below. The list of batch servers must be of the form: host_name1:ip1,hostname2:ip2,.... For fully qualified hostnames, the IP address may be left out. By default, this field will contain any `batch_server` pod(s) you may be running, plus batch.sciencedata.dk.

By providing a public SSH key you can access your container via SSH.

The image will pull your X.509 key and certificate from ScienceData. For this to work, you _must_ tick off `Allow internal HTTP access from your own pods` and click `Generate new personal X.509 certificate` in your [ScienceData settings/preferences](https://sciencedata.dk/index.php/settings/personal#panel-userapps).

The image is pulled from our Docker registry. Build recipes are available on [GitHub](https://github.com/deic-dk/sciencedata_images).
