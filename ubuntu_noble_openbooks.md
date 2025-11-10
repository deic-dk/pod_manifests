Applying this manifest will start Ubuntu Linux 24.04 LTS (Noble Numbat) - running the OpenSSH server and the **openbooks** e-books utility.

openbooks is configured to serve data off the directory `/home/openbooks/ebooks`.

The directory `/home/openbooks/ebooks` is mounted from your ScienceData home server. The path to the folder which is mounted is specified below. This path is relative to either your homedir, [`/files/`](/index.php/apps/files), or [`/storage/`](/storage/) on your ScienceData home server. You should choose the latter, i.e. `/storage/`. `/files/` is mounted read-only - which is not what you want. Read more on `/storage/` [here](https://sciencedata.dk/sites/developer/ManagingFiles/index#storage).

Conveniently, you can mount the same directory to both a Kavita and an openbooks pad - allowing you to immediately serve/read books you've downloaded.

By providing a public SSH key you can access your container via SSH.

The image is pulled from our Docker registry. Build recipes are available on [GitHub](https://github.com/deic-dk/sciencedata_images).
