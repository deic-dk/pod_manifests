Applying this manifest will start Ubuntu Linux 24.04 LTS (Noble Numbat) - running the OpenSSH server and the **Lyrion** music server.

After you firing up this image the first time, visit the web page served and choose a location of your music folder.

The directory `/home/lyrion/music` is mounted from your ScienceData home server. The path to the folder which is mounted is specified below. This path is relative to either your homedir, [`/files/`](/index.php/apps/files), or [`/storage/`](/storage/) on your ScienceData home server. In the former case, it is mounted read-only. Read more on `/storage/` [here](https://sciencedata.dk/sites/developer/ManagingFiles/index#storage).

To keep music across pod deletion/creation, choose the location of your music folder under `/home/lyrion/music`.

When deleting a pod, your `cache` and `prefs` directories will be copied to `lyrion_config.tar.gz` in your ScienceData home folder. When firing up the image again, this archive, if present, will be copied over and used - and thus you'll continue where you left.

By providing a public SSH key you can access your container via SSH.

The image is pulled from our Docker registry. Build recipes are available on [GitHub](https://github.com/deic-dk/sciencedata_images).
