#### CS 340 Class Notes Summer 2021 
# Lecture 3: Command Line Utilities
(05/07/2021)

## Loops and Conditionals

### For-loops in Command Line:
Note: Spaces in the syntax is **meaningful**.  Various commands will not work without the spaces. 

```
> for (( i = 0; i < variable; i + 1)) 
> do
> loop body ...
> ...
> ...
> done
```
### If-statements in Command Line

```
> if [ truthstatement ]
> then
> statement body ...
> else               (optional)
> statement body ... (optional)
> fi
```
You can also use various flags, such as -f or -d to check if a path conforms to some rule, like it is a file or a directory. The following will check if **f** is a file. 

```
> if [ -f filepath ]
```

If-statements in the command line actualy make use of the test program, which simply finds a truth value for some argument(s). The test program is simple the square brackes: [ f filepath ].  

**If** also can run any given command and check the exit code; 0 if true, 1 if false. So, you can write a program that uses **if** and only has an else condition for if the original command failed. 

## Command Substitution 
We can use command substitution to combine multiple commands on the same line, or essentially treat the output of one command as a variable. The following line   of code will run **foo** first, then use that as a variable in the for loop. 

```
> for (( i = 0; i < $(foo); i++))
```

## Output Redirection

We can send the output of an expression to a file, instead of it appearing in the terminal. For example, the following line of code will send a list of files with the filename testanswers to a text file answers.txt.  

```
> find testanswers > answers.txt
```

Note: this will overwrite an existing file, so don't reuse a filename unless you don't care about the contents of the files being erased.   
If we don't want to overwrite a file, the following line will append any output to answers.txt

```
> find test2answers >> answers.txt
```
Also, if a program fails, it will not send anything to the standard output. It will send an error message to the error output. If you are looking for that, the following line of code will send any errors from the program **foo** to error.txt.

```
> foo arg 2> error.txt
```

## Using Directories

### Useful Commands

* **pwd**: Stands for "present working directory". Returns a filepath to your current directory.
* **rm**: Remove file(s).
* **sudo**: Stands for "superuser do", allows you to do things only allowed with administratice access (if you have it).
*  **mkdir**: Make a directory, followed by the name of the new directory.
*  **cd**: Change directory. Can be followed by a tag or filepath, but defaults to home directory.

## Additional Useful Commands and Expressions

* **grep**: Searches for files that fit a specific pattern. Ex: *test.pdf will find all files that end in test.pdf. 
* **curl**: Opens a url.
* **tar xzf**: Unzips a zip file. 
* **basename**: Takes a filepath and returns only the name of the file and the extension. 
* **dirname**: Takes a filepath and returns only the directory path.
* **less**: Turns output into a file, instead of printing it onto the terminal.
* **sort**: Sorts given values, alphabetical by default, numerical with -g.
* **uniq**: Removes duplicates that are next to each other.
























