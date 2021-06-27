Applying this manifest will start a **Jupyter Notebook server** with kernels for Python, R and Julia.

Notebooks are loaded and saved from and to your ScienceData home folder.

Inside the pod/container, your ScienceData  home server/silo can be accessed w/o password over the trusted/internal network by curl'ing to https://sciencedata.dk/files/.

The image is pulled from our [public repository on DockerHub](https://hub.docker.com/r/sciencedata/jupyter_sciencedata).

To enable MATLAB you need to run the command below in a shell inside the pod/container:

```
export SETUP_MATLAB=true && /usr/local/bin/start-notebook.d/setup-software.sh
```

To enable Mathematica you need to run the command below in a shell inside the pod/container:

```
export SETUP_MATHEMATICA=true && /usr/local/bin/start-notebook.d/setup-software.sh
```

Then reload the web page.

For Mathematica to work, you may need to shut down and restart the kernel ("Kernel"->"Shutdown", "Kernel"->"Restart").

