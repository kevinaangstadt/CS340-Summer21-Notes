#### CS 340 Class Notes Summer 2021
# Lecture 11: Test Suite Quality Metrics
(05/26/2021)

## **Overview**

* **Measuring Test Suite Quality**
* **Statement Coverage**
* **Branch Coverage**
* **User Focused Testing**


### Measuring Test Suite Quality

The general way we measure the quality of our test suites is with **code coverage**. A test covers a requirement of a program, such as a line or a branch, if it executes code or checks that requirement. This increases our confidence in our testing by a general negation: If we never test line x, then testing cannot rule out that presence of a bug on line x.   

Testing a particular line does not mean it can't have a bug, but it increases our condifence of such a thing than if it were never tested. 

**Assumptions**  

* We gain the same confidence/information for each visited line.
* The amount of confidence we gain increase for each line.
* Any tests that visit the same lines provide us with the same information.


Our assumptions are obviously not entirely correct, but they allow us to think generally about the scope and quality of our test suite. Test Suite Quality Metrics assess the quality of a suite with respect to an external notion of utility, with allows us to compare different test suites to each other. 

### Statement Coverage

**Statement Coverage** is the same as line coverage, and it measures the lines executed by our test suite relative to the total amount of lines in the entire source code. 

How do we collect the coverage? We use **Coverage Instrumentation** wich modified the program to track coverage while minimizing the observer effect.   

Possible problems:  

* We could achieve 100% statement coverage and still have a bug.
* Input differences could reveal bugs on lines that were covered.
* Line coverage doesn't capture the context of the lines executed, like branches created by conditionals.


### Branch Coverage

**Branch Coverage** measures the coverage in terms of branches created by conditionals. Branch coverage metrics are skewed to prioritize entire branches instead of individual lines.  

Branch coverage subsumes line coverage (100% branch coverage implies 100% line coverage, and is generally a more highly valued metric). 

Branch coverage is more expensive than line coverage because it takes more involved test suites to achieve high coverage. 

### User Focused Testing

Another philosophy is that bugs experienced by users are the most important, so we could potentially only test the possible inputs a user could submit. 

Then, we could simply sample from user-inputs.  

* Sample most common inputs
* Sample most harmful inputs

Confidence = *sample/total inputs

*In this case, we must consider statistical sampling error, and be sure to stratify our samples. 

**Alpha Testing** is the first stage of employing this strategy by dispersing code to developers and internal testers.   
**Beta Testing** is then used to disperse code to a subset of the users and use the inputs from the users to continue testing and gather information.   
**A/B Testing** is the practice of putting out two versions of something, like two-pronged beta testing, and then going with whichever verion has better user response. 





























