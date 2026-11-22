Applying this manifest will start Ubuntu Linux 24.04 LTS (Noble Numbat) running **Moodle 5.3** (long-term support release) and a bundled PostgreSQL database. It is intended primarily for trying out Moodle.

The directory `/var/moodledata` is mounted from `/storage/`on your ScienceData home server and holds Moodle's files (course material, uploads). The path to the folder which is mounted is specified below. Read more on `/storage/` [here](https://sciencedata.dk/sites/developer/ManagingFiles/index#storage).

You log in with your ScienceData account, as Moodle's administrator - no extra password. The members of the groups you tick under **Who may log in** log in with theirs - one group per course: each group becomes a cohort in Moodle, which a course enrols once. How to set up your teaching: [the Moodle guide](ubuntu_noble_moodle.guide.md).

The database runs on the container's local disk and is backed up to `moodle_db-foldername.sql.gz` in the folder `Containers` in your ScienceData home folder every hour and when the container is deleted - where `foldername` is the name of the mounted folder. When a new container is started with the same folder, the backup is loaded, so courses and accounts persist across restarts.

If other sites link to it or embed from your container, it is recommended to check **persistent ports** in the container listing - once it has started.

By providing a public SSH key you can access your container via SSH.

The image is pulled from our Docker registry. Build recipes are available on [GitHub](https://github.com/deic-dk/sciencedata_images).
