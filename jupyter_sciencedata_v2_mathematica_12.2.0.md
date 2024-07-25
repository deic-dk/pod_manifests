Applying this manifest will start a **Jupyter Notebook server** with kernels for Python, R, Julia, ROOT and **Mathematica**.

_Notice: Mathematica is only available to DTU staff and students._

The "HTTPS URL" column will initally be populated with a URL without "token=". After a while, this URL will be updated to include a token and clicking it will allow you to access your server.

Notebooks are loaded and saved from and to your ScienceData home folder, i.e. what you see in the file browser is the same as what you see in the ScienceData files view ("Home").

From a notebook or shell, your ScienceData  home server/silo can be accessed w/o password over the trusted/internal network via HTTP at https&colon;//sciencedata/files/.

The image is pulled from our Docker registry. Build recipes are available on [GitHub](https://github.com/deic-dk/sciencedata_images).

For Mathematica to work, you may need to shut down and restart the kernel ("Kernel"->"Shutdown", "Kernel"->"Restart").
