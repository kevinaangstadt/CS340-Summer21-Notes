#### CS 340 Class Notes Summer 2021
# Lecture 4: Shell Scripting/Editors  
(05/20/2021)

## Commands
* chown: change owner (username : group : file)
* chmod +x <file>: change modifier, the +x is adding the execute modifier, there are others like read (r) and write (w). To remove a modifier use "-", like -x
* ~/: start at the home directory
* mkdir -p <path/to/file>: makes all the directories alongthe path 
* ls -l: "Long form output" ownership | size | permisions 


## Programs
- tmux : Terminal multiplexer which allows us to connect to a persistant shell on a computer
- - tmux ls : shows if a session exists
- - tmux -a : reconnects to a session
- - Discontect from a session <ctr+B, D>
- - Vertical Split: <ctrl+B,%> (has to be a %(shft+5))
- - Horizontal SplitL <ctrl+B,">(has to be a "(shft+'))

- nano <name.txt>: Opens the text editor nano. Notice: adding a name will make a new file in the current dir
- - Exit: <ctrl+x>

- vim <name.txt>: Opens the text editor vim. Notice: adding a name will make a new file in the current dir
- - i: insert mode
- - Esc: command mode, or back to command mode (if you're in trouble... ESC). Most commands start with  a ":"
- - :q! : "quit bang", quit without saving
- - :wq : save and quit (Wumbo and quit, cause I wumbo, you wumbo, he/she/we wumbo [DONT ASK ME WHY ITS THE SAVE KEY I DONT KNOW])


## Notes
bash = born again shell (butter and steak hasbrowns)
To start a new shell you gotta tell it what to run with in this case it would be bash
#!/bin/bash

#! : shebang - tells the program what to use to interpret the file when it's used as an executable

try also: #!/user/bin/env python3 (This makes a python script! Nifty)

To give a file permissions:
