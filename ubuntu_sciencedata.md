### YAML Description

This file contains the configurations for deploying a container of an **Ubuntu Linux 20.04 LTS (Focal Fossa)** image. The image is provided by *sciencedata.dk* and pulled by the public sciencedata repository on [DockerHub](https://hub.docker.com/r/sciencedata/ubuntu_focal_sciencedata). 

Your data is persisted by mounting the container's directory specified in the `mountPath` item to a dedicated folder on `sciencedata.dk/storage/<folder-name>` where `<folder-name>` is the name of your choice. 

You need to provide a valid public SSH key, so that after creation you can access the container locally via SSH connection.  

