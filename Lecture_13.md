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