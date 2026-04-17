Applying this manifest will start a standard **adminer** 4 image - use it to manage any PostgreSQL pods you may be running.

For more info, see:

https://www.adminer.org/

By providing a public SSH key you can access your pod via SSH.

The pod comes with a minimal amount of software installed.
Installing more with `apt` is possible, but notice that it will be gone once the pod is shut down or restarted.

The image is pulled from Docker Hub.

