### YAML Description

This file contains the configurations for deploying a container of an **Ubuntu Linux 20.04 LTS (Focal Fossa)** image. The image is provided by **sciencedata.dk** and pulled by our public repository on [DockerHub](https://hub.docker.com/r/sciencedata/ubuntu_focal_sciencedata). 

Your data is persisted by mounting the container's directory specified in the `mountPath` item to a dedicated folder on `sciencedata.dk/storage/<folder-name>` where `<folder-name>` is the name of your choice. 

By providing a valid public SSH key, you can access the container locally after its creation via an SSH connection.  

