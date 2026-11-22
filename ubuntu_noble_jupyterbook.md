Applying this manifest will start Ubuntu Linux 24.04 LTS (Noble Numbat) with **Jupyter Book** and a web server, publishing the Jupyter Book whose sources are in the folder you choose below.

Keep the book's sources - Markdown pages, notebooks, `_config.yml` and `_toc.yml` - in an ordinary folder in your ScienceData files and choose it below (under `/files/`). Edit them as you like, in the Files app or in a synced folder on your computer: the book is built again by itself after every change and published at the container's address. A broken change does not take the book down - the previous version stays online, and the build log tells what went wrong.

Make a public link to the book's folder, and the pages made from notebooks get a **Run on ScienceData** button: readers open the notebook in their own notebook server on ScienceData. How to set it up: [the Jupyter Book guide](ubuntu_noble_jupyterbook.guide.md).

It is recommended to check **persistent ports** in the container listing - once it has started - so that the book's address stays the same.

The image is pulled from our Docker registry. Build recipes are available on [GitHub](https://github.com/deic-dk/sciencedata_images).
