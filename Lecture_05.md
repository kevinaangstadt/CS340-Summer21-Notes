# Lecture 5 Notes

## New Commands
- `tmux -ls` - view of how many sessions are active
- `tmux a` - attach to tmux session
- `ls - l <file>` - long form output for ls. Permissions will appear in the form:
    + -{user permissions}-{group permissions}-{other permissions} {owner} {group} {file size in bytes} {modified date} {file name}
    + an '@' indicates extended permissions

## Shell Script
- Recall how we need a 'shbang' (`#!`) at the top of a shell script file. This tells the shell what program to run this file. 
- We also need to change file modifier `chmod +x` to make it an executable. 
- To access the command line arguments, the shell conveniently creates an array of strings with the executed command and its args. e.g. `["./covid.sh", "New York"]`. 
- We can access these variables by their index, namely `$0`, `$1`, and so on. 
- Note that accessing an undefined variable gives an empty string, which is useful to check if a command-line arg was provided.
- The following are equivalent ways of checking if a first command-line argument was provided:
    + `if [ $1 ]`
    + `if [ -n $1 ]` - `-n` checks for non empty string. `-z` would check if it is empty. 
- For variable assignment, we add no spaces around `=`. 
    + `state=$1`
- Integer math in a shell script needs to be surrounded by `$(())` to indicate to the shell that these values are not strings
    + `echo 2 + 2` - 2 + 2 
    + `echo $(( 2 + 2))` - 4
- Reminder: `cut` works on input or on a file, so we can echo a variable before piping it it to `cut`


## Covid Script
- To convert cumulative to daily total covid cases we have to iterate across cases and deaths and subtract the current number from the previous number. 


##  Tmux Navigation
- Tmux does not let us do normal scrolling 
    + We could pipe executable into `less` to see the result and scroll here
    + We can go into copy and paste mode in tmux with `{` in command mode. Get out with *esc*

## Bonus: Making Flags
- Creating flags can get a little gnarly since they can show up in any order in the command line
- getopt is a program that is useful for command-line options
