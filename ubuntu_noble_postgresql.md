Applying this manifest will start Ubuntu Linux 24.04 LTS (Noble Numbat) - running the OpenSSH server and the **PostgreSQL** database server.

**Before running this image, you must have generated ScienceData X.509 credentials and have ticked off `Allow internal HTTP access from your own pods` - in your [preferences](/index.php/settings/personal#panel-userapps).**

If you choose "Instance type" **disk2tb** or **disk4tb**, the directory "/mnt", containing the MongoDB data files directory "/mnt/postgresql", is persistent across deletions and recreations of the pod. Notice that if you create several pods from this image, each will have it's own data directory - tied to the name of of the pod, i.e. the contents of "/mnt" will be different, but persistent, for each pod name. If you do not choose instance type, the database data is ephemeral, i.e. gone when the pod is gone.

PostgreSQL runs on the default port 5432 - reverse proxied to a high external port number, which you can inspect in the fold-out panel in the pod listing. You can make this number persistent, once the pod has started.

You can connect to PostgreSQL from the outside  with your ScienceData certificate and key plus the ScienceData CA certificate - all of which you can download in your [preferences](/index.php/settings/personal#panel-userapps).

By providing a public SSH key, you can access your container via SSH.

The image is pulled from our Docker registry. Build recipes are available on [GitHub](https://github.com/deic-dk/sciencedata_images).
