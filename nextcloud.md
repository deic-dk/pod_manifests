Applying this manifest will start **A pod running Nextcloud on top of Caddy, inside Ubuntu 24.04**.

This pod is for testing only: The database backend is SQLite running off a file in NFS.

Caddy is configured to serve data off the directory `/var/www/`.

The directory `/var/www/` is mounted from your ScienceData home server. The path to the folder which is mounted is specified below. This path is relative to [`/storage/` on your ScienceData home server](/storage/). Read more on the storage service [here](https://sciencedata.dk/sites/developer/ManagingFiles/index#storage).

If the folder you mount is empty, it will be populated by a standard Nextcloud installation with minimal apps. If it is populated, it is assumed that this is from a previous installation and nothing will be changed - i.e. your files and the SQLite database with file information etc. will be kept.

By providing a public SSH key you can access your pod via SSH.

The image is pulled from our Docker registry. Build recipes are available on [GitHub](https://github.com/deic-dk/sciencedata_images).

