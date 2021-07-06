#### CS 340 Class Notes Summer 2021
# Lecture 12: Mutation Testing and Test Input Generation   
(05/28/2021)

## Testing Review
What are some useful metrics for our test suite?

### Code coverage 
- Line (or statment) coverage 
    + Used to see how many/ which lines of code our suite executes
- Branch Coverage
    + Each time we have a conditional, what percentage of the time do we go both ways

Limitations of Coverage Metrics
- Increases confidence that a line is working correctly but does not guarantee it
    + Consider what is our confidence of it being correct if we do not even run that line of code
    + Ideal: multiple tests running a line with different inputs to increase our confidence
- Rudamentary, does not necessarily tell us more abput the test suite than the lines executed
- Dead code or irrelevant code might skew coverage metrics 

It can be very difficult to predict what user inputs might be. However we can sample these, for example via beta testing, to get a more accurate image of how to test our code. There are a couple limitations to this:
- Sampling Error
    + Data collected was wrong or not enough to represent population accurately
    + Physics wave example: not sampling with enough frequency might lead us to believe a sinusoidal wave is actually linear
- Sampling Bias
    + We are not getting an accurate representation from our specific sample
    + Statistics can help us solve this based on theoretical distributions

## Mutation Testing
Let us motivate the origin of mutation testing via the strategies we might use to say evaluate two blood hounds. Maybe we hide (artifically place) something for them to look for, and then compare how many objects or how fast they hide them. What if we hide bugs in our programs and see which tests actually find these bugs, and how many. This is what we call mutation testing or analysis. (Only as good as the added bugs). 

### Bugs and Defects
- Defect seeding is the process of adding defects to a program
- Tangent Alert for the History Buffs:
    + The first bug was a literal insect that got stuck in a computer
- We want our bugs to be similar to real bugs/defects that might hide in our codebase
    + Historical bugs we might see in our codes like switching boolean operators, off by one errors, index out of bounds, incorrect arithmetic operator, etc.
- We are going to change our code base with automation
    + Mutation Operators (MO): example patterns/rules for seeding defects

Some common examples of mutation operators include switching boolean or arithmetic operators and switching the order of variable assignments and function calls.
'''
if (a < b) ->  if (a == b)
a = b + c  ->  a = b - c
x = y      ->  y=x
f(); g();  ->  g(); f(); 
'''

### Mutants
A mutant (variant) is a version of the original program produced by applying one of more MO. The **order** is the number of MO applied. Hopefully the test suite can find the mutants, this gives us more confidence that convergae alone since we get a sense that the test suite has previously identified code we know to be buggy. 

Why does this work:
- **Competent Programmer Hypothesis**
    + Faults in programs are syntactically small and can be corrected with a few keystrokes
    + If a test suite can find artifical mutants, it should also be good at finding bugs since they are also syntactically small bugs
    + **BUT** not all bugs are small!
- Because we want them to work since this gives a convient metric
    + We have motivation to model more complex bugs via higher order mutants
    + This is known as the ***Coupling Hypothesis**, the idea that complex faults are combinations of small faults
- Note that tests that detect simple mutants can detect over 99% of 2nd and 3rd order mutants, which seems reasonable evidence for the two reasons provided
- However there are still other kinds of more complex bugs we might not be able to find via mutation testing

## Topic 2

### Maybe this one is a list of steps or commands
* listed item
* listed item
* **command**: explanation
* **command -flag**: explanation

## Topic 3

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
