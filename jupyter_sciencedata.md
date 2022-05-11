Applying this manifest will start a **Jupyter Notebook server** with kernels for Python, R and Julia.

The "HTTPS URL" column will initally be populated with a URL without "token=". After a while, this URL will be updated to include a token and clicking it will allow you to access your server.

Notebooks are loaded and saved from and to your ScienceData home folder, i.e. what you see in the file browser is the same as what you see in the ScienceData files view ("Home").

From a notebook or shell, your ScienceData  home server/silo can be accessed w/o password over the trusted/internal network via HTTP at https://sciencedata/files/.

The image is pulled from our [image repository](https://github.com/deic-dk/sciencedata_images) and hosted in our in-house docker registry.

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

