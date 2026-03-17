Applying this manifest will start Ubuntu Linux 24.04 LTS (Noble Numbat) - running the OpenSSH server and the **MongoDB** database server.

The directory "/mnt", containing the MongoDB data files directory "/mnt/mongodb", is mounted locally from the node hosting the pod and is persistent across deletions and recreations of the pod. Notice that if you create several pods from this image, each will have it's own data directory - tied to the name of of the pod, i.e. the contents of "/mnt" will be different, but persistent, for each pod name.

MongoDB runs on the default port 27017 - reverse proxied to a high external port number. If you're the only one running the image, and noone else has reserved the port, you'll get port 27017, otherwise a random number - which you can, however choose to be persisten once the pod has started.

Locally you can authenticate as 'admin' - with password 'secret' - which you should change.

You can authenticate from the outside with your ScienceData X.509 key and certificate: **You must have generated these in your  [preferences](https://sciencedata.dk/sites/developer/ManagingFiles/index#toc_head3) before running this image.**

Notice that `mongod` is running with the same key/certificate as `certificateKeyFile`.

By providing a public SSH key, you can access your container via SSH.

The image is pulled from our Docker registry. Build recipes are available on [GitHub](https://github.com/deic-dk/sciencedata_images).
