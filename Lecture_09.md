#### CS 340 Class Notes Summer 2021
# Lecture 9: Quality Assurance and Testing
(5/21/2021)

## **Overview**
* **Types of Software Quality**
* **Rice's Theorem**
* **Types of Testing**


#### Types of Software Quality
There is both **Internal** and **External** Quality of software.  

**Internal Quality** is developer-facing quality. The dominant activity of Software Engineering is maintencance, so internal quality is mostly a measure of maintainability.   

How do we ensure Maintainability?  

* Have other developers review our code
* Use good documentation
* Use programming idioms + design patters (more on that later)
* Follow local coding standards
* Code Analysis tools (linters)


**External Quality** is customer-facing or user-facing quality. This mainly means the software "does the right thing". This means,   

* Code doesn't crash or create security issues
* Behaves according to the specifications
* Is robust against maintenance tasks (fixing bugs or adding features doesn't break the overall code)


#### Rice's Theorem

So, why don't we just write a new program, X, that tells us if our software Y is correct?