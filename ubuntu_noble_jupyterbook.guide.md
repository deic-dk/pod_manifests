# Publishing a Jupyter Book

This image publishes a [Jupyter Book](https://jupyterbook.org) - a book or course site written as Markdown pages and Jupyter notebooks - from a folder in your ScienceData files. You write; the container builds and publishes. No Python installation, no build commands, no copying to a web server.

## How it works

- **The sources stay in your ScienceData files**, in an ordinary folder: the Markdown pages and notebooks, `_config.yml` (the book's settings) and `_toc.yml` (its table of contents). Edit them in the Files app, or in a folder on your computer synced with the ScienceData client.
- **The book is built by itself.** The container looks at the folder every 20 seconds; after a change it builds the book again (Jupyter Book 1, the version most course books use) and publishes it at the container's address. A build takes from seconds to minutes, depending on the notebooks it runs.
- **A broken change does not take the book down.** If a build fails, the previous version stays online. What went wrong is in the build log, at `/_sciencedata/build.log` on the book's address.

## Starting

1. Put your book's sources in a folder in your ScienceData files - or, to start from scratch, an example book: Jupyter Book's own [template](https://github.com/executablebooks/cookiecutter-jupyter-book) or any course book you have.
2. In **Containers**, choose **New** and the **Jupyter Book** image.
3. Choose the book's folder under `/files/`. The container reads it, and never changes it.
4. Once the container runs, check **persistent ports** in the container list, so that the book's address stays the same.
5. Open the container's link. The first build may take a minute.

Books in a Git repository work the same way: keep a checkout in a synced folder.

## Run on ScienceData

Make a public link to the book's folder (Share → share link, without a password). From the next build on, every page made from a notebook (`.ipynb`) gets a **Run on ScienceData** button. A reader who clicks it gets their own copy of the notebook, opened in their own notebook server on ScienceData - logged in with their ScienceData account, or as a guest in a temporary server. Their changes are their own; your book is not touched.

The public link also makes the folder's files downloadable by anyone with the link - which suits an open book. Without a link, there are no Run buttons, and the sources stay private (the published book itself is public either way).

Pages written as Markdown get no button - only notebooks can be run.

## Notebooks that run when the book is built

Notebooks without stored outputs are run when the book is built (Jupyter Book's default, `execute_notebooks: auto`), in the container with Python and the common scientific packages - NumPy, SciPy, pandas, Matplotlib, SymPy. With `execute_notebooks: cache` in `_config.yml`, results are cached and a notebook runs again only when it changes; with `off`, nothing is run and the outputs stored in the notebooks are published. A notebook needing other packages fails to execute: save it with its outputs, or set `off`.

## Several books

One container publishes one book. For several, start one container per book folder.
