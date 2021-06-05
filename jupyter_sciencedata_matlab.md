Applying this manifest will start a **Jupyter Notebook server** with kernels for Python, R, Julia and MATLAB.

Inside the pod/container, your ScienceData  home server/silo can be accessed w/o password over the trusted/internal network by curl'ing to https://sciencedata.dk/files/.

The image is pulled from our [public repository on DockerHub](https://hub.docker.com/r/sciencedata/jupyter_sciencedata).

TODO: Notebooks are loaded and saved from and to your ScienceData home folder.