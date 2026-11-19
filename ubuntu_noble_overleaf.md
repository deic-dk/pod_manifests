Applying this manifest will start **Overleaf**, the collaborative LaTeX editor - the extended Community Edition, which adds comments and track changes - with the full TeX Live and its database in the same container.

**Who may log in**: The drop-down above includes ScienceData groups you own; if you choose one, its members can log in, i.e. get an account, via ScienceData. For personal use, choose "Just me". As administrator you can in any case create accounts independently of ScienceData (Admin → Manage users). IN other words, you, as the owner of the container, control who can access the container. Remember also to white-list IP addresses your collaborators work from (below, once the container has started).

**Who has access to what**: All account holders on the container can create projects and share them with each other. _Notice_: Everyone with an account can compile LaTeX in this instance, and a LaTeX compile can in principle read all projects on the container: therefore, _allow only people you trust on your container_.

Projects live in the container. They are backed up to `overleaf_backup-container_name.tar` in the folder `Containers` in your ScienceData home folder - every night and when the container is deleted - and restored when you start the container again. To keep a copy of a project as ordinary files, download it from Overleaf (Menu → Download → Source).

Overleaf is reached at the HTTPS address shown for the container; its links and invitations use that address, so it is recommended to check **persistent ports** in the container listing - once it has started.

By providing a public SSH key you can access the container as root via SSH.

The image is pulled from our Docker registry. Build recipes are available on [GitHub](https://github.com/deic-dk/sciencedata_images).
