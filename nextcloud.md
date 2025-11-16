Applying this manifest will start **A pod running Nextcloud-30.0.2 on top of Caddy on Ubuntu 24.04**.

Nextcloud is installed in `/var/www/nextcloud/`. The directory `/var/www/data` is mounted from your ScienceData home server. The path to the folder which is mounted is specified below. This path is relative to either your homedir, [`/files/`](/index.php/apps/files), or [`/storage/`](/storage/) on your ScienceData home server. In the former case, it is mounted read-only. Read more on `/storage/` [here](https://sciencedata.dk/sites/developer/ManagingFiles/index#storage).

If you choose to mount from `/storage/`, data is kept in the mounted directory `/var/www/data` and is thus persistent across deleting and recreating the pod.

If you choose `/files/`, a user `kube` is created. You can set the password of this user from the admin account. A softlink, named "sciencedata" is created in the homedir of the user `kube` to `/var/www/data` (mounted from ScienceData). This  allows you to view files (read-only) from your ScienceData homedir.

The database backend is SQLite running off a file in the volatile pod filesystem and copied over to `owncloud.db.gz` in the root of your ScienceData homedir when the pod is deleted. If `owncloud.db.gz` exists in this location it is fetched and unpacked when a new pod is created. Notice that if you change which directory is mounted, before starting a new pod, you should also delete `owncloud.db.gz` in your ScienceData homedir.

By providing a public SSH key you can access your pod via SSH.

The image is pulled from our Docker registry. Build recipes are available on [GitHub](https://github.com/deic-dk/sciencedata_images).

