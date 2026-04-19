Applying this manifest will start **A pod running Nextcloud-30.0.2 on top of Caddy, on Ubuntu 24.04**.

This pod is for development only. A first deployment can take 30+ minutes.

For a quicker deployment, use the image `nextcloud`.

Nextcloud is installed in `/var/www/nextcloud/nextcloud`. Data is kept in `/var/www/nextcloud/data`.

The database backend is SQLite running off a file in NFS, i.e. quite slow.

The directory `/var/www/` is mounted from your ScienceData home server. The path to the folder which is mounted is specified below. This path is relative to [`/storage/` on your ScienceData home server](/storage/). Read more on the storage service [here](https://sciencedata.dk/sites/developer/ManagingFiles/index#storage).

If the folder you mount is empty, it will be populated by a standard Nextcloud installation with minimal apps. If it is populated, it is assumed that this is from a previous installation and nothing will be changed - i.e. your files and the SQLite database with file information etc. will be kept.

NOTICE: The above implies that on a first launch, you'll need patience, as installing Nextcloud on an NFS volume will take minutes. Also, it is not advised to run more than one pod off the same directory with this image.

By providing a public SSH key you can access your pod via SSH.

The image is pulled from our Docker registry. Build recipes are available on [GitHub](https://github.com/deic-dk/sciencedata_images).

