#### CS 340 Class Notes Summer 2021
# Lecture 20: Delta Debugging Conclusion
(06/16/2021)

## Delta Debugging Review
Recall the first half of delta debuggin looks like binary search, but we have the *glorious* third condition that lets us do "binary search" on both halves. 

#### A pseudo-python reference implementation:
```python
def DD({c_1, ..., c_n}, required={}):
	if n == 1:
		{c_1}
	let P1 = {c_1, ..., c_n/2}
	let P2 = {c_(n/2 + 1), ..., c_n} 

	if interesting(required.union(P1)):
		return DD(P1, required)

	elif interesting(required.union(P2)):
		return DD(P2, required)

	else:
		return DD(P1, required.union(P2)).union(DD(P2, required.union(P1)))
```

This implementation of delta debugging, namely how the else uses a union of two recursive calls on different partitions, allows us to look for interesting sets that are greater than one. 

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
