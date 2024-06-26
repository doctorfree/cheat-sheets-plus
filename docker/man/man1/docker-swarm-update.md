# NAME

docker-swarm-update - Update the swarm

# SYNOPSIS

**docker swarm update \[OPTIONS\]**

# DESCRIPTION

Update the swarm

# OPTIONS

**--autolock**\[=false\] Change manager autolocking setting (true|false)

**--cert-expiry**=2160h0m0s Validity period for node certificates (ns|us|ms|s|m|h)

**--dispatcher-heartbeat**=5s Dispatcher heartbeat period (ns|us|ms|s|m|h)

**--external-ca**= Specifications of one or more certificate signing endpoints

**-h**, **--help**\[=false\] help for update

**--max-snapshots**=0 Number of additional Raft snapshots to retain

**--snapshot-interval**=10000 Number of log entries between Raft snapshots

**--task-history-limit**=5 Task history retention limit

# SEE ALSO

**docker-swarm(1)**
