#### CS 340 Class Notes Summer 2021
# Lecture 13: Code Coverage   
(mm/dd/2021)


### Path Coverage
Path coverage subsumes branch coverage

If there are N sequential (serial) if-statements
- 2N branch edges -> 2 tests
- 2^N paths -> 2^N tests

b^N -> for b branches of a node with N serial b-branch nodes
- switch/case

```python
if
elif
elif
elif
else
```

```
switch(c) {
	case 1:
	case 2:
	case 3:
	...

}
```

**DEFN:** A **Path Predicate** (path condition or path constraint) is a boolean formula over program variables that is true when the program executes the given path.

**EX:** Path Predicate: false->false->true

Path Predicate 
```
(a >= b) && (c >= d) && (e < f)
```
If this is true, our program will execute the desired pattern:
a = 0, b = 0, c = 0, d = 0, e = 0, f = 1

How do we compute satisfying assignments for path prdicates?
- Human
	- Lot of work
- Random inputs
	- Works really well when answers no sparse
- Use an automated theorem prover
	- Works really well for restricted kinds of equations

Issue -> Infinitely many paths

Each execution of a loop produces a new path


### Approximate
- Only a cyclic path (take  loop 0 or 1 times)
- Take the loop "K" times (unrolling loop K times)
- Enumerating paths depth/breadth first and stop after K paths have been enumerated

**EX:**
```
foo(a,b):
	str1 = get_url(...) # a & b dont control path
	str2 = get_url(...)

	if str1 = str2:
		bar()
```

Solution:
- Give controlled data
	- What does test input mean?
- Don't care
- Ask solver (theorm prover) to only give answers in terms of variables we control
- Do our best (partial assignment)

Did we win?

How do we know the "correct" answr for our inputs?

We are missing the oracle from our oracle-compare to testing model

Test generation
- Bug finding
- If program crashes (implicit oracle) on input == bad! 
- Ex: Automatically generating inputs of death

In geberal, we really want both input and expected output

Oracles are thought to be as difficult to write down formally as it is to write the program correctly

**Oracle Problem** difficulty and cost of determining the correct test oracle for a given input

Can we use the pogram itself as an oracle?

Competent Programer Hypothesis
- Program is mostly correct 

**EX:**
Run program with 10 inputs:
index == array-len -1

Perhaps our oravle could be:
assertEquals(indes, array-len-1)
- Should be true every time we run

**DEFN:** A **invariant** is a predicate (boolean expression) over program varaiable that is true on every execution of that program
- Can serve as oracles

We will learn (or infer) program invariants by running the program many times and then note what is always true of the output

**EX:** sqrt() => return value >= 0

Assumption: Common behavior == correct behavior 
- When this assumption fails:
	- EX: run sqrt(9) learn ret-val == 3
		- run more tests with different inputs
	- EX: test "findNode" 1000 times and learn pointer%4 == 0
		- artifact of our system
		- it cost money to check something we dont care about

Competent Programers
- Each line of code matter for correctness
- generate mutants
	- falsify invariant -> Keep
	- never falsify -> Threo it out

This is an example of search-based software engineering (SBSE)

In reality at companies there are too many tests!
- auto-gen -> often low-quality

### Test Suite Minimization Problem
Given a set of test cases and coverage information for each test, find the minimal number of test cases that still have mazimum coverage.

**EX:**
|T  | numbers  |
|---|----------|
|T1	|1,2,3     |
|T2	|  2,3,4,5 |
|T3 |1,2       |
|T4 |1,       6|


