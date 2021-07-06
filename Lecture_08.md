#### CS 340 Class Notes Summer 2021
# Lecture 08: GitHub and Repositories
(mm/dd/2021)


## Information in Commit
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

Try to keep commits small:
- Easier to troubleshoot
- Easier to revert
- Easier to review
- Easier to blame

**Useful Commands**
* **git add --patch**: Pick/choose what to stage
* **git add -**: Pick/choose what to stage


## A Bit More on Remotes
Once you push to a remote...

Each remote gets a "name" in your local repo

Configuration:
- By default the remote from which you clonedthe repository is called "origin"

RW Repo (Origin) ---fetch---> Local Repo (Branch: Main, feature-1) <---fetch--- RO repo (Upstream)

^^^^^^^->>--------<<---^^^^^^^^^^--->>-------------------------<<-^^^^^^^

Sudo lables to the remote: 
- origin/main
- origin/feature1-1
- upstream/main

**pull request:** Request for a developer to pull your commits onto the upstream repository
- same rules apply forpull request as with commits

**Typical Workflow:**
1. Assign yourself to the issue in the bug tracker (or open an issue and assign self)
2. Fork repository/clone
3. make new branch for changes
4. Commit changes to new branch
5. Push to the fork
6. Open pull request
	- Return to step 4

### **Commands**
reset/revert: create a new commiot that undoes some changes
- undoes changes by copying the version of the file from another commit
- **git reset --hard HEAD:** Resets working directory
- **git reset --soft HEAD:** Resets only staging directory


# Quality Assurance and Testing
- Want to deliver high-quality software at a low cost
- How do we measure, assess, or assure software quality?

**DEFN: Quality Assurance** *is the maintenance of a desired level of quality in a service or product especially by means of attention to every stage of the process of delivery or production.*

Two finds of quality:
1. External (Customer-facing)
	- programs should "do the right thing"
2. Internal (developer-facing)
	- program should be readable, maintainable, etc,...