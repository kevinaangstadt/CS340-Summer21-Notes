#### CS 340 Class Notes Summer 2021
# Lecture 12: Mutation Testing and Test Input Generation   
(05/28/2021)

## Testing Review
What are some useful metrics for our test suite?

### Code coverage 
- Line (or statement) coverage 
    + Used to see how many/ which lines of code our suite executes
- Branch Coverage
    + Each time we have a conditional, what percentage of the time do we go both ways

Limitations of Coverage Metrics
- Increases confidence that a line is working correctly but does not guarantee it
    + Consider what is our confidence of it being correct if we do not even run that line of code
    + Ideal: multiple tests running a line with different inputs to increase our confidence
- Rudimentary, does not necessarily tell us more about the test suite than the lines executed
- Dead code or irrelevant code might skew coverage metrics 

It can be very difficult to predict what user inputs might be. However, we can sample these, for example via beta testing, to get a more accurate image of how to test our code. There are a couple of limitations to this:
- Sampling Error
    + Data collected was wrong or not enough to represent population accurately
    + Physics wave example: not sampling with enough frequency might lead us to believe a sinusoidal wave is linear
- Sampling Bias
    + We are not getting an accurate representation from our specific sample
    + Statistics can help us solve this based on theoretical distributions

## Mutation Testing
Let us motivate the origin of mutation testing via the strategies we might use to say evaluate two bloodhounds. Maybe we hide (artificially place) something for them to look for, and then compare how many objects or how fast they hide them. What if we hide bugs in our programs and see which tests find these bugs and how many. This is what we call mutation testing or analysis. (Only as good as the added bugs). 

### Bugs and Defects
- Defect seeding is the process of adding defects to a program
- Tangent Alert for the History Buffs:
    + The first bug was a literal insect that got stuck in a vacuum tube machine on a boat
- We want our bugs to be similar to real bugs/defects that might hide in our codebase
    + Historical bugs we might see in our codes like switching boolean operators, off-by-one errors, index out of bounds, incorrect arithmetic operator, etc.
- We are going to change our code base with automation
    + Mutation Operators (MO): example patterns/rules for seeding defects

Some common examples of mutation operators include switching boolean or arithmetic operators and switching the order of variable assignments and function calls.
```
if (a < b) ->  if (a == b)
a = b + c  ->  a = b - c
x = y      ->  y=x
f(); g();  ->  g(); f(); 
```

### Mutants
A mutant (variant) is a version of the original program produced by applying one or more MO. The **order** is the number of MO applied. Hopefully, the test suite can find the mutants, this gives us more confidence than coverage alone since we get a sense that the test suite has previously identified code we know to be buggy. 

Why does this work:
- **Competent Programmer Hypothesis**
    + Faults in programs are syntactically small and can be corrected with a few keystrokes
    + If a test suite can find artificial mutants, it should also be good at finding bugs since they are also syntactically small bugs
    + **BUT** not all bugs are small!
- Because we want them to work since this gives a convenient metric
    + We have the motivation to model more complex bugs via higher-order mutants
    + This is known as the **Coupling Hypothesis**, the idea that complex faults are combinations of small faults
- Note that tests that detect simple mutants can detect over 99% of 2nd and 3rd order mutants, which seems reasonable evidence for the two reasons provided
- However, there are still other kinds of more complex bugs we might not be able to find via mutation testing

What does MT measure?
- Percent of mutants found by the test suite
    + Also known as Mutation Adequacy score

### Limitations
Mutation Testing is expensive
- A lot of computations to runs
    + Run the whole test suite which could be of hundreds of tests, hundreds of times for each mutant individually
- Equivalent Mutant Problem
    + Detecting equivalent mutants, which will all pass the same tests
    + Note these might not look the same but might logically be the same
    + Recall how everything that is about the meaning of a program, which equivalence is, is a non-trivial question that we cannot write something nice to figure out -> Rice's Theorem (plug to CS380: Theory of Computation)

## Test Input Generation
Wait, where do all these tests come from? and what even is a test case?
- A *test case* has three components:
    + The **test input**: the date we give into the program
    + The **test oracle**: the expected output
    + The **comparator**: something that compares the real and expected outputs
    + This model is called the Oracle-Comparator model 

### Comparator
In many cases, we do an exact match but we can have more general or partial matches. 
- Error bounds on numbers/ rounding errors
- Ignore dates or times

### Test inputs
How do we get these?
- Humans may generate them
- Computer
    + Automatic generation can make life easier
    + Often we want to optimize for a metric, for example, code coverage
    + This might be useful information about the program under a test
    + Let's consider branch coverage

Let's run through an example of how we might automate test input generation to optimize for branch coverage of the following code.
```python
def foo1(a, b, c, d, e, f):
    if a < b : this
    else: that
    if c < d: foo
    else: bar
    if e < f: baz
    else: qux
```

We can make a control flow graph (CFG) to see the branches we need to cover, in this case, it is only six. Note that we need at most two tests to cover all branches, however, we can also look at all the possible paths we could take. This is known as path coverage and it is the percent of paths through the CFG we cover. Note that there are $2^n$ paths where $n$ is the number of conditionals to consider. 

