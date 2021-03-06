Applying this manifest will start **Ubuntu Linux 20.04 LTS (Focal Fossa)** - running the Dropbear SSH server and the Caddy web server.

Dropbear is configured to serve data off the directory `/root/www/container_host_name/`, where `container_host_name` is the hostname of your container.

The directory `/root/www/` is mounted from your ScienceData home server. The path to the folder which is mounted is specified below. This path is relative to [`/storage/` on ScienceData](https://sciencedata.dk/sites/developer/ManagingFiles/index#toc_head9).

By providing a public SSH key you can access your container via SSH.

The image is pulled from our [public repository on DockerHub](https://hub.docker.com/r/sciencedata/ubuntu_focal_sciencedata).

