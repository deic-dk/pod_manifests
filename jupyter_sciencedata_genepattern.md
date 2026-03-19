Applying this manifest will start a **Jupyter Notebook server** using a customized version of the Docker image provided by the GenePattern group: https://notebook.genepattern.org/.

**Before running this image, you must have ticked off `Allow internal HTTP access from your own pods` - in your [preferences](/index.php/settings/personal#panel-userapps).**

The "HTTPS URL" column will initally be populated with a URL without "token=". After a while, this URL will be updated to include a token and clicking it will allow you to access your server.

Notebooks are loaded and saved from and to your ScienceData home folder, i.e. what you see in the file browser is the same as what you see in the ScienceData files view ("Home").

From a notebook or shell, your ScienceData  home server/silo can be accessed w/o password over the trusted/internal network via HTTP at https&colon;//sciencedata/files/.

