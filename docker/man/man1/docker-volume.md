# NAME

docker-volume - Manage volumes

# SYNOPSIS

**docker volume COMMAND**

# DESCRIPTION

The `docker volume` command has subcommands for managing data volumes. A data volume is a specially-designated directory that by-passes storage driver management.

Data volumes persist data independent of a container's life cycle. When you delete a container, the Docker daemon does not delete any data volumes. You can share volumes across multiple containers. Moreover, you can share data volumes with other computing resources in your system.

To see help for a subcommand, use:

>     docker volume COMMAND --help

For full details on using docker volume visit Docker's online documentation.

# OPTIONS

**-h**, **--help**\[=false\] help for volume

# SEE ALSO

**docker(1)**, **docker-volume-create(1)**, **docker-volume-inspect(1)**, **docker-volume-ls(1)**, **docker-volume-prune(1)**, **docker-volume-rm(1)**
