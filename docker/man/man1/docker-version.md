# NAME

docker-version - Show the Docker version information

# SYNOPSIS

**docker version \[OPTIONS\]**

# DESCRIPTION

This command displays version information for both the Docker client and daemon.

# EXAMPLES

# Display Docker version information

The default output:

>     $ docker version
>     Client:
>      Version:      1.8.0
>      API version:  1.20
>      Go version:   go1.4.2
>      Git commit:   f5bae0a
>      Built:        Tue Jun 23 17:56:00 UTC 2015
>      OS/Arch:      linux/amd64
>
>     Server:
>      Version:      1.8.0
>      API version:  1.20
>      Go version:   go1.4.2
>      Git commit:   f5bae0a
>      Built:        Tue Jun 23 17:56:00 UTC 2015
>      OS/Arch:      linux/amd64

Get server version:

>     $ docker version --format '{{.Server.Version}}'
>     1.8.0

Dump raw data:

To view all available fields, you can use the format `{{json .}}`.

>     $ docker version --format '{{json .}}'
>     {"Client":{"Version":"1.8.0","ApiVersion":"1.20","GitCommit":"f5bae0a","GoVersion":"go1.4.2","Os":"linux","Arch":"amd64","BuildTime":"Tue Jun 23 17:56:00 UTC 2015"},"ServerOK":true,"Server":{"Version":"1.8.0","ApiVersion":"1.20","GitCommit":"f5bae0a","GoVersion":"go1.4.2","Os":"linux","Arch":"amd64","KernelVersion":"3.13.2-gentoo","BuildTime":"Tue Jun 23 17:56:00 UTC 2015"}}

# OPTIONS

**-f**, **--format**="" Format the output using the given Go template

**-h**, **--help**\[=false\] help for version

**--kubeconfig**="" Kubernetes config file

# SEE ALSO

**docker(1)**
