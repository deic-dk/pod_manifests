Applying this manifest will start a **Jupyter Notebook server** with kernels for Python, R and Julia.

Notebooks are loaded and saved from and to your ScienceData home folder, i.e. what you see in the file browser is the same as what you see in the ScienceData files view ("Home").

Notice that browsing directories, creating new files and directories is lagging and there's no indication that things are actually loading. So, you'll just have to have a bit of patience.

From a shell inside the pod/container, your ScienceData  home server/silo can be accessed w/o password over the trusted/internal network by curl'ing to https://sciencedata/files/.

The image is pulled from our [repository on DockerHub](https://hub.docker.com/r/sciencedata/jupyter_sciencedata).

To enable MATLAB, run the command below in a shell inside the pod/container:

```
export SETUP_MATLAB=true && /usr/local/bin/start-notebook.d/setup-software.sh
```

To enable Mathematica, run the command below in a shell inside the pod/container:

```
export SETUP_MATHEMATICA=true && /usr/local/bin/start-notebook.d/setup-software.sh
```

Then reload the Jupyter web page.

For Mathematica to work, you may need to shut down and restart the kernel ("Kernel"->"Shutdown", "Kernel"->"Restart").

