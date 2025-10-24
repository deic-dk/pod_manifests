Applying this manifest will start a **Jupyter Notebook server with the JupyterLab web UI** and kernels for Python, R, Julia and ROOT.

The "HTTPS URL" column will initally be populated with a URL without "token=". After a while, this URL will be updated to include a token and clicking it will allow you to access your server.

Notebooks are loaded and saved from and to the volatile pod storage. Thus, if you want to preserve your work, you need to manually upload it somewhere, e.g. to sciencedata.

From a notebook or shell, your ScienceData  home server/silo can be accessed w/o password over the trusted/internal network via HTTP at https&colon;//sciencedata/files/.

The image is pulled from our Docker registry. Build recipes are available on [GitHub](https://github.com/deic-dk/sciencedata_images).

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

_Notice: MATLAB and Mathematica are only available to DTU staff and students._
