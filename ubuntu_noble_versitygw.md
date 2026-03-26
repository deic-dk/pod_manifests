Applying this manifest will start Ubuntu Linux 24.04 LTS (Noble Numbat) - running the OpenSSH server and **Versity S3 Gateway**.

Versity S3 Gateway is configured to serve data off the directory `/mnt/vgw/`. The service will be accessible from the outside via HTTPS at the assigned port - which can be read off the pod listing.

The directory `/mnt/vgw/` is mounted from your ScienceData home server. The path to the folder which is mounted is specified below. This path is relative to [`/storage/`](/storage/) on your ScienceData home server. Read more on `/storage/` [here](https://sciencedata.dk/sites/developer/ManagingFiles/index#storage).

You can configure the S3 service by editing the config file "/mnt/vgw/versitygw.conf", following the [documentation](https://github.com/versity/versitygw/wiki).

Users are identified by their access key ID and authenticate with this and their secret access key. You can read off the secret access key of the admin user, in the config file.

You can add additional users with:

```
versitygw admin -a admin -s ADMIN_SECRET_ACCESS_KEY -er http://127.0.0.1:7070 create-user -r user -a USER_ACCESS_KEY_ID -s USER_SECRET_ACCESS_KEY
```

where `ADMIN_SECRET_ACCESS_KEY` is the secret access key of the admin user, `USER_ACCESS_KEY_ID` is the access key ID of the new user (any string) `USER_SECRET_ACCESS_KEY` is the secret access key of the new user (any string).

By providing a public SSH key you can access your container via SSH.

The image is pulled from our Docker registry. Build recipes are available on [GitHub](https://github.com/deic-dk/sciencedata_images).
