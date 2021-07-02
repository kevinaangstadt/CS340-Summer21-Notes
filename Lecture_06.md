#### CS 340 Class Notes Summer 2021

# Lecture 6: Version Control Systems

(05-14)

## Goals

- Redundancy: retaining files in the face of hardware/software failures

- Collaboration

- Log of past changes
    - revert to past changes
    - you can see who made a change, "blaming" the person who owns the commit
    - understand original purpose/history of a project (this is useful for adding new features)

## Related goals
- building the project into a larger management tool
    
- tracking bugs/issues
    
- handling proposed patches

- automatically building/testing/release code
    
- documenting functionality

## Two architectures for VCSs

**Centralized**: uses a single server which hosts the history/versions of all of the files. Clients "check out" a specific version of a file and can "check in" their changes.
   
   - PROS:
       - one history everyone agrees on
   - CONS:
       - doesn't resolve redundancy
       - you need to connect to the server for any operation
       
A slightly antiquated example of a centralized VCS is <a href="https://subversion.apache.org/">SVN</a>.  

**Distributed**: each copy of the repository contains the full history of the repo.
    
   - PROS:
       - resolves redundancy, to an extent
       - shared history among participants
       - flexibility
       - offline functionality
   - CONS:
       - can become costly in storage
       - history != history' != history''
           - reconcile/resolve history
    

## How does a DVCS keep track of changes to files (i.e. snapshots)?

**OPTION 1**: Store a full copy of every file when a user "checks in" or "commits" their changes. This is a big contributor to storage costs, though.

**OPTION 2**: Store the differences or changes to files (*deltas* or *diffs*). This keeps track that were deleted and/or inserted. To get a version of a file, you're essentially replaying through all of the deltas. This can be achieved through git with commands like `diff` or `patch`.

**OPTION 3**: Only store a new copy of the file when there are changes (snapshots). This can often be combined with compression.

**With each commit to a VCS, we will always store**:

- author
- email
- timestamp
- message describing the change
    - often referred to as "prose", this will consist of anything ranging from a small summary to a detailed description

**Often commit when you've**:

- completed a task
- completed a subtask/checkpoint
- "left" the code for a while
- share your changes with others

### How to commit a file:

When on a new device, it's best to get it acquired to your Github credentials. Using `git configure --global`, it's a priority to edit the:

    - user.name
    - user.email
    - core.editor
fields to your name, Github account email, and preferred terminal/cmdline editor.

From here, assuming you have a directory in mind (if not, create one using `mkdir [directoryname]`), you're ready to start adding/committing/pushing files!

- `git status` is useful, even if you're fairly confident of your repo's status. You'll see which files have been modified, which ones are ready for staging, etc.
- `git add [filename]` will add the file to the staging process.
- `git commit` will redirect you to your editor (whichever one that may be). You'll be able to write a message describing the file and/or its changes. You can also add a `-m` flag to write a shorter message.
- `git push` will push the file(s) added.