# YAML Description

The ubuntu_sciencedata.yaml contains all the relevant information, so the users can run an Ubuntu Focal Fossa container using the image that Sciencedata provides.  In the yaml file, under the metadata section, it is specified the image that is used from the Sciencedata's repository on DockeHub along with the path where persistent volume is mounted into the container. The ports that the container is listening to are also specified in the yaml file because the ubuntu container will only be accessible by the users if they run an ssh server on port 22 and a web server on port 80. The users have to provide their public ssh key to access the container. 

## Docker Image Description

Runs an Ubuntu Linux 20.04 LTS (Focal Fossa) container through sciencedata.dk
