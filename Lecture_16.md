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

        **Severity**
    : Degree of impact a defect has on dev. or operation of SW
    - cost to not fix

        **Priority**
    : Importance or urgenct of fixing

3. **Assignment**: Who will work on this bug?
    - Based on "ownership"
    - Destributed: developers watch the bug queue and claim reports
    - Cetralized: QA people watch the queue and assign reports to a pool of developers

4. **Bug Resolution**: Did we fix it?
    - done the work for the report
    - Resolution Status: result of the most recent attempt to adress the report
        - **not** necessarily fixed

5. **Send to QA**

6. **Reopen**
    - Evidence that previous resolution is insufficient
        - new bug reports
        - no longer out of scope
        - QA/testing finds mistakes
    - cf. regression testing