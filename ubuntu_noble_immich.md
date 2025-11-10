Applying this manifest will start Ubuntu Linux 24.04 LTS (Noble Numbat) - running the OpenSSH server and the **Immich** photo/video server.

The directory `/var/lib/immich/media` is mounted from your ScienceData home server and used for photo and video storage. The path to the folder which is mounted is specified below. This path is relative to either your homedir, [`/files/`](/index.php/apps/files), or [`/storage/`](/storage/) on your ScienceData home server. In the former case, it is mounted read-only. Read more on `/storage/` [here](https://sciencedata.dk/sites/developer/ManagingFiles/index#storage).

If you choose to mount `/files/`, you're assumed to manage your content from ScienceData and upload functionality is disabled in Immich.

After firing up this image the first time, you should visit the `view` URL listed below, create an administrator account and create an external library with a path under `/var/lib/immich/home/media`, i.e. serve content from the directory mounted from ScienceData.

When deleting a pod, a dump of your database is copied to `immich_data.sql` in your ScienceData home folder. When firing up the image again, this file, if present, is copied over and loaded - and thus your configuration, including user accounts, will be persistent across restarts. If you're mounting from `/files/`, after a restart you'll have to regenerate thumbnails by clicking

    Administration -> Jobs -> GENERATE THUMBNAILS -> ALL

By providing a public SSH key you can access your container via SSH.

The image is pulled from our Docker registry. Build recipes are available on [GitHub](https://github.com/deic-dk/sciencedata_images).
