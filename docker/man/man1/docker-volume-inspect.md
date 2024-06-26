# NAME

docker-volume-inspect - Display detailed information on one or more volumes

# SYNOPSIS

**docker volume inspect \[OPTIONS\] VOLUME \[VOLUME...\]**

# DESCRIPTION

Returns information about one or more volumes. By default, this command renders all results in a JSON array. You can specify an alternate format to execute a given template is executed for each result. Go's ⟨https://golang.org/pkg/text/template/⟩ package describes all the details of the format.

# OPTIONS

**-f**, **--format**="" Format the output using the given Go template

**-h**, **--help**\[=false\] help for inspect

# SEE ALSO

**docker-volume(1)**
