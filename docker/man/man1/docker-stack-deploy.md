# NAME

docker-stack-deploy - Deploy a new stack or update an existing stack

# SYNOPSIS

**docker stack deploy \[OPTIONS\] STACK**

# DESCRIPTION

Deploy a new stack or update an existing stack

# OPTIONS

**--bundle-file**="" Path to a Distributed Application Bundle file

**-c**, **--compose-file**=\[\] Path to a Compose file, or "-" to read from stdin

**-h**, **--help**\[=false\] help for deploy

**--namespace**="" Kubernetes namespace to use

**--prune**\[=false\] Prune services that are no longer referenced

**--resolve-image**="always" Query the registry to resolve image digest and supported platforms ("always"|"changed"|"never")

**--with-registry-auth**\[=false\] Send registry authentication details to Swarm agents

# OPTIONS INHERITED FROM PARENT COMMANDS

**--kubeconfig**="" Kubernetes config file

**--orchestrator**="" Orchestrator to use (swarm|kubernetes|all)

# SEE ALSO

**docker-stack(1)**
