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
