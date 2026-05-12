Applying this manifest will start Ubuntu Linux 24.04 LTS (Noble Numbat) - running the OpenSSH server and **Versity S3 Gateway**.

Versity S3 Gateway is configured to serve data off the directory "/mnt/vgw/". The service will be accessible from the outside via HTTPS at the assigned port - which can be read off the pod listing.

The directory "/mnt/vgw/" is mounted from your ScienceData home server and data is thus persistent across pod restarts. The path to the folder which is mounted is specified below. This path is relative to [`/storage/`](/storage/) on your ScienceData home server. Read more on `/storage/` [here](https://sciencedata.dk/sites/developer/ManagingFiles/index#storage).

Since NFS does not support extended attributes, metadata is kept in a "sidecar" in "/tmp/versitygw".

You can configure the S3 service by editing the config file "/mnt/vgw/versitygw.conf", following the [documentation](https://github.com/versity/versitygw/wiki).

Users are identified by their access key ID and authenticate with this and their secret access key. You can read off the secret access key of the admin user, in the config file. To use it, set environment variables:

```
source /mnt/vgw/versitygw.conf
```

You can add then additional users with:

```
versitygw admin -er http://127.0.0.1:7070 create-user -r user -a USER_ACCESS_KEY_ID -s USER_SECRET_ACCESS_KEY
```

where `USER_ACCESS_KEY_ID` is the access key ID of the new user (any string) `USER_SECRET_ACCESS_KEY` is the secret access key of the new user (any string).

To access the service, you can also use the [AWS command line tools](https://awscli.amazonaws.com/) - preinstalled on the pod.

Create a bucket with:

```
aws s3api --endpoint-url http://127.0.0.1:7070 create-bucket --bucket mybucket
```

List buckets with:

```
aws --endpoint-url http://127.0.0.1:7070 s3api list-buckets
```

Upload a file with:

```
aws --endpoint-url http://127.0.0.1:7070 s3api put-object --bucket mytest-bucket --key some_file --body some_file
```

From the outside, replace `127.0.0.1:7070` with `kube.sciencedata.dk:port_number`, where `port_number` can be read off the container list below.

You can also use S3 GUI clients, like [Cyberduck](https://cyberduck.io). For Cyberduck to work with Versitygw, you have to enable and use the profile ("Preferences"/"Settings"->"Profiles") "S3 (Deprecated path style requests)".

When deleting a pod, your metadata directory, "/tmp/versitygw", will be archived to "versitygw-foldername.tar.gz" in your ScienceData home folder - where `foldername` is the name of the directory mounted from ScienceData. When firing up the image again, this archive, if present, will be copied over and used.

By providing a public SSH key, you can access your container via SSH.

The image is pulled from our Docker registry. Build recipes are available on [GitHub](https://github.com/deic-dk/sciencedata_images).
