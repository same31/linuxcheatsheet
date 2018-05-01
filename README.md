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

-r : recursive

-l : only list files

## awk

Extracts the first column of output

`awk '{print $1}'`

## tac

Reverse output (reverse cat)

or `tail -r`
