Applying this manifest will start **Ubuntu Linux 22.04 LTS (Jammy Jellyfish)**
with a default set of **CVMFS** repositories mounted and a default setup script
sourced at boot time. You can changed both in the relevant input fields.

Notice that clearing the list of CVMFS repositories causes the default set to
be mounted, whereas clearing the setup script causes no script to be sourced.

By providing a public SSH key you can access your pod via SSH.

The pod comes with a minimal amount of software installed.
The idea is to use software from "/cvmfs/*".
Installing more software with `apt` is possible, but notice that it will be gone once the pod is shut down or restarted.

The image is pulled from our Docker registry. Build recipes are available on [GitHub](https://github.com/deic-dk/sciencedata_images).

