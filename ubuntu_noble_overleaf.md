Applying this manifest will start **Overleaf**, the collaborative LaTeX editor - the extended Community Edition, which adds comments and track changes - with the full TeX Live and its database in the same container.

On the first start, an administrator account is created for you, with your ScienceData user ID as e-mail address. As administrator you can create accounts for collaborators (Admin → Manage users), and share projects with them in Overleaf.

Everyone with an account can compile LaTeX in this instance, and a LaTeX compile can read the other projects in it: _share an instance only with people you trust with all of its projects_.

Projects live in the container. They are backed up to `overleaf_backup-container_name.tar` in the folder `Containers` in your ScienceData home folder - every night and when the container is deleted - and restored when you start the container again. To keep a copy of a project as ordinary files, download it from Overleaf (Menu → Download → Source).

Overleaf is reached at the HTTPS address shown for the container; its links and invitations use that address, so it is recommended to check **persistent ports** in the container listing - once it has started.

By providing a public SSH key you can access the container as root via SSH.

The image is pulled from our Docker registry. Build recipes are available on [GitHub](https://github.com/deic-dk/sciencedata_images).
