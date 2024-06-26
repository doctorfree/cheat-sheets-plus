# NAME

docker-image-import - Import the contents from a tarball to create a filesystem image

# SYNOPSIS

**docker image import \[OPTIONS\] file|URL|- \[REPOSITORY\[:TAG\]\]**

# DESCRIPTION

Create a new filesystem image from the contents of a tarball (`.tar`, `.tar.gz`, `.tgz`, `.bzip`, `.tar.xz`, `.txz`) into it, then optionally tag it.

# EXAMPLES

# Import from a remote location

>     # docker image import http://example.com/exampleimage.tgz example/imagerepo

# Import from a local file

Import to docker via pipe and stdin:

>     # cat exampleimage.tgz | docker image import - example/imagelocal

Import with a commit message.

>     # cat exampleimage.tgz | docker image import --message "New image imported from tarball" - exampleimagelocal:new

Import to a Docker image from a local file.

>     # docker image import /path/to/exampleimage.tgz 

# Import from a local file and tag

Import to docker via pipe and stdin:

>     # cat exampleimageV2.tgz | docker image import - example/imagelocal:V-2.0

# Import from a local directory

>     # tar -c . | docker image import - exampleimagedir

# Apply specified Dockerfile instructions while importing the image

This example sets the docker image ENV variable DEBUG to true by default.

>     # tar -c . | docker image import -c="ENV DEBUG true" - exampleimagedir

# When the daemon supports multiple operating systems

If the daemon supports multiple operating systems, and the image being imported does not match the default operating system, it may be necessary to add `--platform`. This would be necessary when importing a Linux image into a Windows daemon.

>     # docker image import --platform=linux .\linuximage.tar

# See also

**docker-export(1)** to export the contents of a filesystem as a tar archive to STDOUT.

# OPTIONS

**-c**, **--change**= Apply Dockerfile instruction to the created image

**-h**, **--help**\[=false\] help for import

**-m**, **--message**="" Set commit message for imported image

**--platform**="" Set platform if server is multi-platform capable

# SEE ALSO

**docker-image(1)**
