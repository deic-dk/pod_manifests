Applying this manifest will start Ubuntu Linux 24.04 LTS (Noble Numbat) - running the OpenSSH server. 

The directory `/home/sciencedata/mnt` is mounted from your ScienceData home server. The path to the folder which is mounted is specified below. This path is relative to [`/storage/` on your ScienceData home server](/storage/). Read more on the storage service [here](https://sciencedata.dk/sites/developer/ManagingFiles/index#storage).

If a folder named `cron.hourly`, `cron.daily`, `cron.weekly` and/or `cron.monthly` is found in the top-level mounted partition, any script files therein, with extension `.sh`, will be executed with the interval inferred from the folder name.

By providing a public SSH key you can access your container via SSH.

The image is pulled from our Docker registry. Build recipes are available on [GitHub](https://github.com/deic-dk/sciencedata_images).
