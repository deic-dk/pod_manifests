Applying this manifest will start **Ubuntu Linux 20.04 LTS (Focal Fossa)**
with a default set of **CVMFS** repositories mounted and a default setup script
sourced at boot time. You can changed both in the relevant input fields.

Notice that clearing the list of CVMFS repositories causes the default set to
be mounted, whereas clearing the setup script causes no script to be sourced.

Providing a public SSH key allows you to access your pod via SSH.

The pod comes with a minimal amount of software installed - plus what's necessary
to run the (CERN centric) software packages of the default setup script.

The idea is to use software from "/cvmfs/*" to process data that can be conveniently
kept on ScienceData and accessed via unauthenticated HTTPS at https&colon;//sciencedata/files/.

Installing more software with `apt` is possible, but notice that it will be gone
once the pod is shut down or restarted.

The image is pulled from our Docker registry. Build recipes are available on
[GitHub](https://github.com/deic-dk/sciencedata_images).

