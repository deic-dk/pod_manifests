Applying this manifest will start Ubuntu Linux 22.04 LTS (Jammy Jellyfish) - running the OpenSSH server and the **Caddy** web server.

Caddy is configured to serve data off the directory `/root/www/`.

The directory `/root/www/` is mounted from your ScienceData home server. The path to the folder which is mounted is specified below. This path is relative to [`/storage/` on your ScienceData home server](/storage/). Read more on the storage service [here](https://sciencedata.dk/sites/developer/ManagingFiles/index#storage).

By providing a public SSH key you can access your container via SSH.

The image is built from our [image repository](https://github.com/deic-dk/sciencedata_images) and hosted in our in-house docker registry.
