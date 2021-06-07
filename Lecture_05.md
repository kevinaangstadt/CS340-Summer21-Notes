# Lecture 5 Notes

## New Commands
- `tmux -ls` - view of how many sessions are active
- `tmux a` - attach to tmux session
- `ls - l <file>` - long form output for ls. Permissions will appear in the form:
    + -{user permissions}-{group permissions}-{other permissions} {owner} {group} {file size in bytes} {modified date} {file name}
    + an '@' indicates extended permissions
- `tail -n +<number>` - gets the lines of a file after the specified number

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
- In arithmetic expansion, *math mode*, the shell recognizes variables without having to use '$'. 
    + `$((var + 42))` as opposed to `$(($var + 42))`
- Reminder: `cut` works on input or on a file, so we can echo a variable before piping it it to `cut`
- Reminder: `grep -i` is for case insensitive message
- To check if a value is in a specific data set, say Paris as a possible state of the US, we can use `[ -z grep $state ]` since `grep` will return an empty string when it nothing is found. 
- Reminder: remove any temporary files with `rm $temp_file` before exiting with `exit <exit code>`

## Covid Script
- Last lecture we accessed a csv file of Covid-19 deaths and cases by day, we will be manipulating this data with a shell script to output more manageable data and allow a user to select a desired state
- To convert cumulative to daily total covid cases we have to iterate across cases and deaths and subtract the current number from the previous number. 

##  Tmux Navigation
- Tmux does not let us do normal scrolling 
    + We could pipe executable into `less` to see the result and scroll here
    + We can go into copy and paste mode in tmux with `{` in command mode. Get out with *esc*

## Version Control Systems
- Recall that maintenance is the dominant activity in software development. 
    + Correcting faults
    + Improving design
    + Implementing Enhancements
    + Fix regressions (part of the code that used to work)
- Software development does not happen in a vacuum
    + Team members
    + Multiple computers
    + Computer crashes

### How do we manage files so that we can support all these activities?
1. Backups (USBs, Hard drives, etc)
    + Pros: 
        - Recover old files
        - Share files
        - Custom versions
    + Cons: 
        - Expensive
        - Scalability
        - Recursive Problem (our backups individually have the same problem we started with)
        - Hard to manage
        - Remember to bring
2. Cloud Storage (Dropbox, OneDrive, etc)
    + Pros:
        - Off-site (always available)
        - Automatic
        - Some versioning
        - Sharing
    + Cons: 
        - Collaboration 
        - Security or privacy concerns (since handled by third party)
        - "Break the build" (say if adding something and saving it automatically breaks our code)
3. Version Control System (git)
    + Modify files
    + Mark files that are ready to be added to the "repository" (global shared files)
    + Bundle up and share our changes with everyone 
    + git is a version control system, GitHub is a website that hosts git repositories
    
## Bonus: Making Flags
- Creating flags can get a little gnarly since they can show up in any order in the command line
- GetOpt is a program that is useful for command-line options

