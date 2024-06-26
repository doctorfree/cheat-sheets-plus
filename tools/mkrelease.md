# Github release creation (CLI)

Convenience shell script to create a Github release from the command line.

Configure the version and release, modify the annotation (`ANNO` variable), and execute this script from the root of your repository hierarchy.

```shell
#!/bin/bash

VERSION="1.0.0"
RELEASE=1

usage() {
    printf "\nUsage: mkrelease [-c] [-d] [-p] [-u]"
    printf "\nWhere:"
    printf "\n\t-c indicates clean first"
    printf "\n\t-d indicates create draft release"
    printf "\n\t-p indicates skip package creation step"
    printf "\n\t-u displays this usage message and exits\n"
    exit 1
}

CLEAN=
DRAFT=
PACKAGE=1
while getopts "cdpu" flag; do
    case $flag in
        c)
            CLEAN=1
            ;;
        d)
            DRAFT="--draft"
            ;;
        p)
            PACKAGE=
            ;;
        u)
            usage
            ;;
    esac
done
shift $(( OPTIND - 1 ))

ANNO="Cheat Sheets Plus, Version ${VERSION} Release ${RELEASE}"

if [ -f Release_Notes.md ]
then
  gh release create v${VERSION}r${RELEASE} ${DRAFT} \
                  --title "${ANNO}" \
                  --notes-file Release_Notes.md
else
  gh release create v${VERSION}r${RELEASE} ${DRAFT} \
                  --title "${ANNO}" \
                  --generate-notes
fi

git fetch --tags origin
```
