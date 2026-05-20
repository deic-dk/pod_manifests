Applying this manifest will start **A pod running Nextcloud on top of Caddy, on Ubuntu 24.04**.

This pod is for development only. A first deployment can take several minutes.

For a quicker deployment, use the image `nextcloud`.

Nextcloud is installed in `/var/www/nextcloud`. Data is kept in `/var/www/data`.

The directory `/var/www/` is mounted from your ScienceData home server. The path to the folder which is mounted is specified below. This path is relative to [`/storage/` on your ScienceData home server](/storage/). Read more on the storage service [here](https://sciencedata.dk/sites/developer/ManagingFiles/index#storage).

If the folder you mount has a subdirectory `nextcloud`, it will be used unchanged. Otherwise, a subdirectory `nextcloud` will be created and populated with a recent minimal Nextcloud, checked out from GitHub.

The SQLite database, "/var/www/data/owncloud.db", with file information etc. is in fact a soft-link to the local file `/tmp/owncloud.db` (for performance), which is backed up to `owncloud.db-dev-foldername.gz` (where `foldername` is the name of the directory mounted from ScienceData) in the root of your ScienceData homedir, when the pod is deleted. When a new pod is created, if this file exists, it is fetched, unpacked and used.

NOTICE: The above implies that on a first launch, you'll need patience, as installing Nextcloud on an NFS volume can take a few minutes. Also, it is not advised to run more than one pod off the same directory with this image.

By providing a public SSH key you can access your pod via SSH.

The image is pulled from our Docker registry. Build recipes are available on [GitHub](https://github.com/deic-dk/sciencedata_images).

