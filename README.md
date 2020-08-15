# Linux Cheat Sheet
Cheat sheet for command lines I will never remember

## find

find WHERE WHAT

`find . -name "*.js" ! -path "./node_modules/*"`

`find . -regex ".*\\.\\(html\\|js\\)"`

*Note the backslash before group brackets and alternation operator. Use `-regextype posix-extended` to get rid of the backslashes*

### options

-maxdepth LEVELS -mindepth LEVELS

-type [fd]

-iname NAME : case insensitive name

-size [+-]SIZE[kMG]

## grep

grep SEARCH IN_FILES

`grep searchString app/* build/*`

### options

-H : file name

-n : line number

-r : recursive

-i : case insensitive

-l : only list files

-v : inverse (filter out)

## awk

Extracts the first column of output

`awk '{print $1}'`

Extracts before last column and append it to a string (needs a white space)

`awk '{print "path/" $(NF-1)}'`

### options

-F',' : Sets ',' as the field separator

## tac

Reverse output (reverse cat) of a file or use a pipe

or `tail -r`

## xargs

Runs a command on every line of input

`ls -l | xargs -I{} echo {}`

Inlines the output of a command (defaults utility to echo)

`ls -l | xargs`

### options

-I{} : Argument placeholder

-n1 : Executes utility for each (one) argument (ie: `-rw-r----- root  root     358 Aug  8 15:00 README.md` is 8 arguments)

-P2 : Parallel mode (2 at a time)

-p : Prompts efore executing every command

## sed

String substitution (global) in file or use a pipe

`sed 's/hello/world/' <file>`

## ln

Create a symbolic link

`ln -s /path/to/fileName linkName`

## du

Disk usage in a directory

`du -shc * | sort -h`

## while

`while read line; do echo "$line"; done;`

## vim

Open result of a command in a buffer

`ls | vim -`

### vim commands

Pipe current file in a command and send back into vim

`:$!sort -u`

Search and replace in the whole file

`%s/search/replace/` (g flag optional at the end if vim configured with gdefault)

Search and replace the last search

`%s//replace/`

Delete all occurences of the last search

`%s///`
