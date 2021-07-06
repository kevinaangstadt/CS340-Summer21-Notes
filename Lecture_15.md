#### CS 340 Class Notes Summer 2021
# Lecture 16: Defect Reports and Triage/ Bug Life Cycle 
(06/07/2021)


### Defect Reporting and Triage

Mozilla (2005): 300 bug reports a day

- How many bugs/day are there now for Mozilla?
    - Bug tracker Bugzilla
    - Last week: ~1000 new bug reports
        - = ~140/day
    A lot to keep up with!

**Fault**
: a fault is an exceptional situation at runtime
- exception/trap

**Defect**
: a defect is any characteristic of a product that hinders its usability for its intended purpose
- ex/ design defect or manufacturing defect
- CS -> a **bug** is a static defect in the source code

**Bug Report**
: a bug report provides information about a defect
- created by tester, user, tool, etc...
- often contain multiple types of info
- often tracked in a DB

**Feature Request**
: a feature request is a potential change to the intended purpose (requirements) of a piece of software

In CS, **Issues** are the union of bug reports and feature requests


### Defect/Bug Reports and Feature Requests Are "Living Beings"

**Defect Report Lifecycle**
: a defect report lifecycle consists of a number of possible stages and activities, including reporting, confirmation, triage, assignment, resolution, and verification
- **not** a linear process
- **Status** of report to track its position in this lifecycle

1. **How do Bugs Enter The Tracker?**
    - Internal: Dev, QA/tester
    - External: beta tester/end users
        - details vary!
        - may not be able to rely on end user describing the defect correctly
            - agregate
    
    #### Anatomy of a Bug Report
    1. Summary/Title
    2. Component-part SW
    3. Version of SW
    4. OS
    5. Long description
        - steps to reproduce
        - actual observed results
        - expected results

        Attachments:
        - screenshots
        - videos
        - stack trace
        - data files

    Defect reports are **dynamic** (not static)
    - updated over time
    - report is a log of all relevant activity

2. **Triage**: Which bug reports do we adress first?
    - assign degrees of urgency
    - Cost-benifit analysis:
        - how expensive is it to fix?
        - how expensive is it to **not** fix?

        **Shell**
    : a program that exposes an OS's servives and programs to a human user
    - text based interface










**Maybe this one is a list of steps or commands**

* listed item
* listed item
* **command**: explanation
* **command -flag**: explanation

### Topic 3

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