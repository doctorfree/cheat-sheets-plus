# NAME

docker-container-wait - Block until one or more containers stop, then print their exit codes

# SYNOPSIS

**docker container wait CONTAINER \[CONTAINER...\]**

# DESCRIPTION

Block until a container stops, then print its exit code.

# EXAMPLES

>     $ docker run -d fedora sleep 99
>     079b83f558a2bc52ecad6b2a5de13622d584e6bb1aea058c11b36511e85e7622
>     $ docker container wait 079b83f558a2bc
>     0

# OPTIONS

**-h**, **--help**\[=false\] help for wait

# SEE ALSO

**docker-container(1)**
