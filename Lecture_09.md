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

**Rice's Theorem** tells us that All non-trivial semantc properties are undecidable. Meaning, we cannot create a machine or any kind of program that can tell if a non-trivial program is correct. We can create an X that is sometimes right, or often right, but we can't always know when it is wrong. (Theory Of Computation Note: this is the proof that Atm doesn't exist.)  

Instead, we can use an approximation of X, with things like type checkers, and we can test. 

#### Types of Testing

**Software Testing**  is an investigation conducted to provide developers and stakeholders with information about the quality of the Software Product or service under test.  Key Concept: Testing increases your confidence that your implementation adheres to the specifications. We do not have any measure of confidence in untested code. 

Typical testing, so far, includes creating inputs with known or expected outputs, and comparing them to the software-generated outputs. This requires an oracle of some kind that knows that expected or 'correct' outputs, which is not always known. 

**Regression Testing** is the practice of building up and regularly running a suite of tests that reveal previous bugs in the code. New tests are added everytime a bug is identified and fixed to prevent the same problems coming back later. These are typically run every time a new feature or patch is added.   

**Unit Testing** involves testing individual units of source code, instead of the entire thing. This applies to a single file, folder, feature, class, etc. Frameworks that help with unit testing include: JUnit, python unittest, c++ googletest, and manyy more. The tests themselves are a form of comparison tests, usually. 

**Test Cases** are a type of test that:  

* Establish a pre-condition that must be true before the program runs
* Performs the operation Ex. "Input must be negative integer", "foo and baz must be initialized"
* Assert a post-condition: check output, side effects, etc.   


A **Test Fixture** might also be used before and after a test to set up the preconditions and clean up any resulting data after. 

















