Applying this manifest will start Ubuntu Linux 24.04 LTS (Noble Numbat) - running the OpenSSH server and the **Caddy** web server.

Caddy is configured to serve data off the directory `/var/www/`.

The directory `/var/www/` is mounted from your ScienceData home server. The path to the folder which is mounted is specified below. This path is relative to either your homedir, [`/files/`](/index.php/apps/files), or [`/storage/`](/storage/) on your ScienceData home server. In the former case, it is mounted read-only. Read more on `/storage/` [here](https://sciencedata.dk/sites/developer/ManagingFiles/index#storage).

This image also comes with a PHP script from https://files.gallery, allowing upload and file management from the browser. To enable it, copy over the content of the "files" directory to your web root:

```
cp -r /var/lib/caddy/files/* /var/www/
```

Then visit the URL BASE_URL/files.php, where BASE_URL is the URL you can read in the column `view` below.

To not have your web root world read/writeable, you should add a user and set a password. This is done by editing the file "config/config.php".

By providing a public SSH key you can access your container via SSH.

The image is pulled from our Docker registry. Build recipes are available on [GitHub](https://github.com/deic-dk/sciencedata_images).
