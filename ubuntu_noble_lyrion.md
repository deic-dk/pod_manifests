Applying this manifest will start Ubuntu Linux 24.04 LTS (Noble Numbat) - running the OpenSSH server and the **Lyrion** music server.

After you firing up this image the first time, visit the web page served and choose a location of your music folder.

The directory `/home/lyrion/music` is mounted from your ScienceData home server. The path to the folder which is mounted is specified below. This path is relative to either your homedir, [`/files/`](/index.php/apps/files), or [`/storage/`](/storage/) on your ScienceData home server. In the former case, it is mounted read-only. Read more on `/storage/` [here](https://sciencedata.dk/sites/developer/ManagingFiles/index#storage).

To keep music across pod deletion/creation, choose the location of your music folder under `/home/lyrion/music`.

When deleting a pod, your `cache` and `prefs` directories will be copied to `lyrion_config.tar.gz` in your ScienceData home folder. When firing up the image again, this archive, if present, will be copied over and used - and thus you'll continue where you left.

To allow connecting clients (music players), the pod serves data via HTTP on port 9000 (web frontend and audio streams) and 3483 (API). These ports are reverse proxied on the external ports listed in the field "external ports". If you're the only one running this pod, your external ports will also be 9000 (TCP) and 3483 (UDP and TCP) - making it straight forward to connect clients. If not, you will have to [set up port forwarding](https://forums.lyrion.org/forum/user-forums/logitech-media-server/105388-problems-getting-squeezeplay-to-work-remotely-over-ssh) in your end, as clients typically use hard-coded port numbers 9000 and 3483.

Notice that the web frontend is also proxied by an HTTPS proxy on the port listed in the "view" column below.

By providing a public SSH key you can access your container via SSH.

The image is pulled from our Docker registry. Build recipes are available on [GitHub](https://github.com/deic-dk/sciencedata_images).
