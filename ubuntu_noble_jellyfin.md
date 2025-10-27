Applying this manifest will start Ubuntu Linux 24.04 LTS (Noble Numbat) - running the OpenSSH server and the **Jellyfin** media server.

After you firing up this image the first time, you should visit the web page served and create an administrator account.

The directory `/home/jellyfin/media` is mounted from your ScienceData home server. The path to the folder which is mounted is specified below. This path is relative to [`/storage/` on your ScienceData home server](/storage/). Read more on the storage service [here](https://sciencedata.dk/sites/developer/ManagingFiles/index#storage).

To keep media across pod deletion/creation, configure jellyfin to use `/home/jellyfin/media` for media storage.

When deleting a pod, your configuration directory will be copied to `jellyfin.tar.gz` in your ScienceData home folder. When firing up the image again, this archive, if present, will be copied over and used - and thus you'll continue with the libraries you configured last time you ran the image.

By providing a public SSH key you can access your container via SSH.

The image is pulled from our Docker registry. Build recipes are available on [GitHub](https://github.com/deic-dk/sciencedata_images).
