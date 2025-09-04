Applying this manifest will start Ubuntu Linux 24.04 LTS (Noble Numbat) - running the OpenSSH server. 

The directory `/home/sciencedata/mnt` is mounted from your ScienceData home server. The path to the folder which is mounted is specified below. This path is relative to [`/storage/` on your ScienceData home server](/storage/). Read more on the storage service [here](https://sciencedata.dk/sites/developer/ManagingFiles/index#storage).

If a folder named `cron.d` is found in the top-level mounted partition, `/etc/cron.d` will be replaced  with a soft-link to this directory. This means that cronjobs can be configured by creating text files in cronjob format inside this folder. These can point to shell scripts. These can source the file `/home/sciencedata/env.sh`, which is created on system start and passes on the Kubernetes environment variables. Example:

```
cat /home/sciencedata/mnt/cron.d/test
*/5 * * * * sciencedata /home/sciencedata/mnt/myscript.sh
```

```
cat /home/sciencedata/mnt/myscript.sh
#!/bin/bash

. /home/sciencedata/env.sh && ( date; echo "This is my ENV:"; env ) >> /tmp/cron.log
```

After making changes to files in `cron.d`, you must restart `cron`:

```
service cron restart
```

By providing a public SSH key you can access your container via SSH.

The image is pulled from our Docker registry. Build recipes are available on [GitHub](https://github.com/deic-dk/sciencedata_images).
