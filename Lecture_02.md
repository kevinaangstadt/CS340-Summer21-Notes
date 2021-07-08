#### CS 340 Class Notes Summer 2021
# Lecture 2: Linux Command Line Utilities
(05/03/2021)

## Commad Line Tools
**Why not use GUI's?**  
- Hard to combine 2 programs with GUI's together
- A lot of the programs we write do not have a GUI

**Why Use Linux?**  
- Is not commonly used for personal comnputers
- Is used for about 3/4 of servers
- Very high market share for servers

**Shell**
: a program that exposes an OS's servives and programs to a human user
- text based interface

**ssh** - secure shell
- connect remotely to another computer and run a shell

## How to connect to the remote server for class
`ssh <username>@cs-linuxlab-<number>.stlawu.local` 
- (Use SLU password)

## Command List:
`pwd` - prints working directory  
`cd <dir name>` - changes into specified directory (default: home)  
`ls` - lists files and directories inside of current directory ("-l" long output, "-h" human readable). 
`clear` - clears command line  
`mkdir <name>` - makes a directory with the given name  
`which <name>` - returns the path to a given program if installed (and in $PATH)  
`curl <URL>` - opens file ar given URL (-Ok)  
`man <name>` - opens the manual for the given program  
^a - brings you to beginning of a command  
^e - brings you to the end of a command  
`tar xzf <filename>` - decompresses a .tar.gz file  
^c - kills a running program  
`find <folder>` - returns the names of all files in a directory  
`echo <string>` - prints a string to the command line  
`grep <pattern> <input>` - searches input for matching patterns ("-i" case insensitive)  
`wc <input>` - gives the number of lines, words, and bytes in the given input ("-l" just outputs number of lines)  
`$(<command>)` - embeds a command inside of another command  
`less` - reader program ("/" to search, q to quit)
 
## Directories
- A directory is a folder
- Root directory is /
- Inside of root is bin, lib, home, ...
- ".." refers to parrent directory
- "." refers to current directory

## Loops
```bash
{
    for i in {<start>..<end>..<increment(optional)>}
    do
    <body>
    done
}
```

```bash
{
    for ((i = <start>; i<= <end>; i++))
    do
    <body>
    done
}
```

```bash
{
    for i in <list>}
    do
    <body>
    done
}
```

**Globbing**
: wildcard characters to match anything meeting the given pattern

A **pipe** ("|") redirects output from one program to be the input to the next progra