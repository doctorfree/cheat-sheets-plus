# csv2md

The `csv2md` command converts a CSV format document to Markdown.

```shell
#!/bin/bash
#
# csv2md - convert CSV format file to Markdown
#
# Adapted by Ronald Record from:
# https://www.log4code.com/converting-a-csv-file-to-markdown-using-sqlite/
#
# Requires sqlite3 3.30.0 or later
#
# Usage: ./csv2md [-h] [-r] file.csv
# Where:    -r indicates remove input CSV file after conversion
#
# Output: file.md

help() {
    printf "\nUsage: ./csv2md [-h] [-r] file.csv"
    printf "\nWhere:"
    printf "\n\t-h indicates display this usage message and exit"
    printf "\n\t-r indicates remove input CSV file after conversion\n"
    exit 1
}

# Set any options to defaults
remove=

# Process all the command line options
while :; do
    case $1 in
        # Two hyphens ends the options parsing
        --)
            shift
            break
            ;;
        -h|--help)
            help
            exit
            ;;
        -r|--remove)
            remove=1
            ;;
        -?*)
            echo "The command line option is unknown: $1"
            help
            ;;
        # Anything remaining is treated as content not a parseable option
        *)
            break
            ;;
    esac
    shift
done

[ -f "$1" ] || {
    echo "$1 does not exist or is not a regular file. Exiting."
    exit 1
}

inputFilename="$1"
baseFilename=`echo ${inputFilename} | sed -e "s/\.csv//"`

outputFile="${baseFilename}.md"
rm -f ${outputFile}

cmd=$({ grep -v '^#' <<EOF
.headers on
.mode csv
drop table if exists temp_csvFile;
.import ${inputFilename} temp_csvFile
.mode markdown
.headers on
.output ${outputFile}
select * from temp_csvFile;
EOF
})

echo -e "${cmd}" | sqlite3 ''

[ "${remove}" ] && rm -f "${inputFilename}"
```
