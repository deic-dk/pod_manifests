Applying this manifest will start **A pod running Nextcloud-30.0.2 on top of Caddy on Ubuntu 24.04**.

Nextcloud is installed in `/var/www/nextcloud/nextcloud`. Data is kept in `/var/www/nextcloud/data`.

The latter directory is mounted from your ScienceData home server. The path to the folder which is mounted is specified below. This path is relative to [`/storage/` on your ScienceData home server](/storage/). Read more on the storage service [here](https://sciencedata.dk/sites/developer/ManagingFiles/index#storage).

The database backend is SQLite running off a file in NFS, i.e. quite slow.

By providing a public SSH key you can access your pod via SSH.

The image is pulled from our Docker registry. Build recipes are available on [GitHub](https://github.com/deic-dk/sciencedata_images).

