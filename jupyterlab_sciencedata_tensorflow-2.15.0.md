Applying this manifest will start a **Jupyter Notebook server with the JupyterLab web UI with a Python kernel and CUDA-enabled TensorFlow-2.15 tools and libraries** (two enabled GPUs).

Use this image to run the <a href="https://www.tensorflow.org/tutorials">official</a> TensorFlow examples - made available <a href="https://sciencenotebooks.dk/urls/sciencedata.dk/public/e282734bb53e03090b22d6d0439960ef/?base_name=TensorFlow">here</a> for convenience.

The "HTTPS URL" column will initally be populated with a URL without "token=". After a while, this URL will be updated to include a token and clicking it will allow you to access your server.

Notebooks are loaded and saved from and to your ScienceData home folder, i.e. what you see in the file browser is the same as what you see in the ScienceData files view ("Home").

From a notebook or shell, your ScienceData  home server/silo can be accessed w/o password over the trusted/internal network via HTTP at https://sciencedata/files/.

The image is pulled from our Docker registry. Build recipes are available on [GitHub](https://github.com/deic-dk/sciencedata_images).

