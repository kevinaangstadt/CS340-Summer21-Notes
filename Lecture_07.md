#### CS 340 Class Notes Summer 2021
# Lecture 7: Git: Branching and Remote Repositories   
(05/17/2021)

## Git Review
- The working directory contains a current version of the files
- Once we are done with edits, we move on to the staging area 
- A commit 'checks in' into the repository 
- Finally, we can checkout from the repository back into our working directory

How are Commits in Repo Related?  
- Commits in a repo form a tree
    + Formally a graph with no cycles
- Git labels commits with a "hash"
    + These are a constant length string
    + Constant length hashes let us optimize for space since we always know how much we are storing (plug for CS:345 Database Systems)
    + Hashes are long and seemingly arbitrary strings, but we only need the part of it that uniquely identifies them
    + **git checkout HASH** is the command to move to a commit (this is best on a clean working directory with no uncommitted changes)
- Git tree is a directed graph, where branches may merge
- At any point in time, the working directory is based on some node in this tree
- When we commit changes, we add a new child to that node in the tree 
    + node (circle) with a new edge (line) from our "starting" commit

## Git Branching
We can also have 'Pointers' or aliases to specific commits in the repo.
- For example, the HEAD: which refers to which commit in the repository is the working directory based on
    + A detached HEAD can occur if we check out an old commit and make a new one without creating a new branch (if we do not use the -b flag)
    + This "branch" will not have a name and can only be accessed with the commit id's
- These are aliases are called branches and when we commit, our label for the branch moves with us
- Other useful commits to label might include the default commit to checkout when cloning a repo
    + This used to be called the master branch but was changed to main due to historical connotations of the word master and association to slavery and colonialism
    + In SVN the main brach is known as the trunk
- Git branches are lightweight because they are just pointers
- We use *ahead* and *behind* to refer to how branches may have newer or older commits in relation to each other
+ Tags are permanent labels we can add to a particular commit
    - We can go back to it if it is important
    - E.g. release versions (v.3.5.27) 

### Making New Branches
- **git checkout -b [BRANCH]**: will make a new branch and check it out
- **git branch [BRANCH]**: will make a new branch at HEAD but does not move the working directory

How do we recombine branches?
1. Rebase - "copy" comments into another branch like a transplant
    + Keeps our history looking linear
    + Lose a bit of the history/topology of our repo
    + Works well for local edits and to organize local work before sharing
2. Merge - combine commits and form a new commit with combined changes (two parents)
    + Bring one of the branches into the history of another branch
    + Full history is maintained
    + If there are conflicts git will prompt the user to solve merge conflicts, git uses special symbols to show where the conflicts lie
    + History can get gnarly (complicated) because crossings in the history
    + Works well with collaborators because it doesn't destroy previous commits
- Note: **git stash** can be used to store uncommitted changes

## Remote Repositories
A *remote repository* is just another copy of the repository, which contains the same commit history. We can share our commits to synchronize the graph of commits between the copies of the repo. 
- These repositories will often be hosted on websites such as GitHub/ GitLab
    - They may have nice interfaces and other features as well

### Remote Commands
- `git remote`: Tell repository that there will be other copies of these repositories
    + add/ remove repositories to remote
- `git clone path`: Download a copy of repository history from a remote repo
    + "origin" remote pointing to where we cloned, this is a remote branch (e.g origin/main)
- `git push`: Share your local history to the remote
- `git fetch`: Gets the updated commit history from the remote 
    + doesn't update your branches or tags but gives the latest origin branches
    + often we git rebase/merge
- `git pull`: git fetch + git merge
    - `-- rebase`: This flag will convert the merge into a rebase instead
