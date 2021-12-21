Applying this manifest will start **Ubuntu Linux 20.04 LTS (Focal Fossa)** - running the Dropbear SSH server.

By providing a public SSH key you can access your container via SSH.

Traffic to the liste "HTTPS URL" is forwarded to port 80 of the pod. This is just for convenience in case it
is needed. The pod does not run anything on port 80.

The image is pulled from our [public repository on DockerHub](https://hub.docker.com/r/sciencedata/ubuntu_focal_sciencedata).

