#### CS 340 Class Notes Summer 2021
# Lecture 08: GitHub and Repositories   
(mm/dd/2021)


### Information in Commit
Commit messages can be several lines long (and should be??)
- Describe the problem being fixed (can reference the bug report number) but description should still be standalone
- Don't assume access to outside resources
- Describe why the changes are being made
- Format:
	- First Line is "Subject"
		- Short desctiption of the commit (Should answer the question: If commited, this commit will...?)
		- Present tesne. Ex: "Fix resizing of main window", "Add sort option to user data table"
	- Subsequent Lines
		- Lines are message body where we add all of the commentary
		- Put blank lines between paragraphs

**Note:** Nano -r 72
- This command will wrap lines at 72 characters, reason: "Because"
- In nano to implement the wraping you must press "ctrl+j"

### **Golden Rule:** The commit message must contain all the information to fully understand and review the patch/changes for correctness.


### Things To Avoid
- Dont mix whtiespace changes with functional code changes
- Dont mix unrelated functional changes
- Dont submit all code as a single commit (rebase/cherry-pick is super helpful)

**Maybe this one is a list of steps or commands**

* listed item
* listed item
* **command**: explanation
* **command -flag**: explanation


#### Topic 3

```bash
> Example bash commands
> find random | grep *1.5
> if [ -f $f ]
> do
> else
> then
> fi
```
Maybe sometimes you need to link something [here](https://en.wikipedia.org/wiki/Main_Page).

### Additional Commands, comments 
* **grep**
* **find**
* **cut**


Project updates (?)  
Resources used















