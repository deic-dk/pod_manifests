
# YAML DESCRIPTION

This file contains the configurations for deploying a container of a **Jupyter Notebook** image. You wil be able to run your data not only in Python but also in R, Matlab and Mathematica. The image is provided by sciencedata.dk and pulled by our public repository on [DockerHub](https://hub.docker.com/r/sciencedata/ubuntu_focal_sciencedata).

Your data is persisted by mounting the container's directory specified in the mountPath item to a dedicated folder on sciencedata.dk/storage/<folder-name> where <folder-name> is the name of your choice.

