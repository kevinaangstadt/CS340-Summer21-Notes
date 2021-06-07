#### CS 340 Class Notes Summer 2021 
# Lecture 4: Remote Servers + Shell Scripting


## **Overview**

*  **Tmux introduction and commands**
*  **Shell Scripting practice**  
  
  

### Why Use a Remote Server?
Remote Servers can run programs continuously without your personal computer being on. 

### tmux
'Terminal Multiplexer' creates a session you can recconect to. Allows you to connect and disconnect from remote servers without ending a session.   

* Initialize a session: **tmux**
* Disconnect from tmux: **[CONTROL** + **B]**  **D**
* Attach to a tmux session: **tmux attach**
* Move between windows: **[CONTROL + B]** arrow keys to move
* Multiple Shells: **[CONTROL + B]** **%** vertical split, **"** horizontal split
* Close out of window **[CONTROL + B]**, **/exit**

### What is a 'script'?
A shell script is similar to a program. It is an executable file. A shell script uses command line arguments, in the case of this class, bash. The terminology 'script' implied the file is for an automatred activity, rather than problem solving.

###Nano/Vim text editors:
What to run:  
**nano example.txt**.  
**vim example.txt**

Quit without saving: **: q !**  
Type insert-mode: **i**  
Save Changes: **: w**  
Quit after saving: **: q**  
Get out of commands: **[ESC]**

### Shell Script Basics

Start the file with a header that tells says where to run this file and what to use. This is for a shell script with bash.   
	**#!/bin/bash**   
I could also run the following line if I wanted a python file.  
	**#!/user/bin/envpython3**  

Now, write a simple bit of code. But, in order to run the file, you have to change it to an executable function. You in order to make a file executable for anyone to run, use the following command.  
	**chmod a +x examplefile.sh**  

This command allows access to anyone, but you can also look at different options with the **chmod** manual page by running **man chmod**.  


### What the heck is "foo"?

'Foo' is among several common metasyntactic variables commonly used by computer scientists. It's similar to 'lorem ipsum', as it is an arbitrary variable that can stand in for any arbitrary thing without implying any specific meaning. There are several like 'foo', including 'bar', 'baz', 'qux', and many more. 




















