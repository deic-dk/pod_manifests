Applying this manifest will start Ubuntu Linux 24.04 LTS (Noble Numbat) - running the OpenSSH server and the **Jellyfin** media server.

After you firing up this image the first time, you should visit the web page served and create an administrator account.

The directory `/home/jellyfin/media` is mounted from your ScienceData home server. The path to the folder which is mounted is specified below. This path is relative to either your homedir, [`/files/`](/index.php/apps/files), or [`/storage/`](/storage/) on your ScienceData home server. In the former case, it is mounted read-only. Read more on `/storage/` [here](https://sciencedata.dk/sites/developer/ManagingFiles/index#storage).

To keep media across pod deletion/creation, configure jellyfin to use `/home/jellyfin/media` for media storage.

When deleting a pod, your configuration directory will be copied to `jellyfin_data.tar.gz` in your ScienceData home folder. When firing up the image again, this archive, if present, will be copied over and used - and thus your configuration, including user accounts, will be persistent across restarts.

By providing a public SSH key you can access your container via SSH.

The image is pulled from our Docker registry. Build recipes are available on [GitHub](https://github.com/deic-dk/sciencedata_images).
