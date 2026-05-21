Applying this manifest will start Ubuntu Linux 24.04 LTS (Noble Numbat) - with the Anthropic Claude command-line tool preinstalled and running the OpenSSH server.

**Before running this image, you must have ticked off `Allow internal HTTP access from your own pods` - in your [preferences](/index.php/settings/personal#panel-userapps).**

The directory `/home/claude/code` is mounted from your ScienceData home server. The path to the folder which is mounted is specified below. This path is relative to [`/storage/`](/storage/) on your ScienceData home server. 

To keep the code you work on across pod deletion/creation, run `claude` in `/home/claude/code`.

When deleting a pod, your Claude session files "/home/claude/.claude*" will be copied to `claude-foldername.tar.gz` in your ScienceData home folder - where `foldername` is the name of the directory mounted from ScienceData. This is also done by an hourly cronjob. When firing up the image again, this archive, if present, will be copied over and you can continue  working where you stopped with `claude continue`.

By providing a public SSH key you can access your container via SSH.

The image is pulled from our Docker registry. Build recipes are available on [GitHub](https://github.com/deic-dk/sciencedata_images).
