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

## DD Performance
We consider the asymptotic runtime complexity, big-O, of an algorithm to understand the abstract limits of how long something will run. This has the form O(f(n)) where f(n) is some upper bound function of 'number of steps' given the size of our input, n, modulo some constant factor. In other words, for some constant c * f(n), this function will always eventually be bigger than our programs number of steps. 

So what is the Big-O of DD? Well we have cases:
- Single Change:
	+ `else` is never called as we will find either P1 or P2 to be interesting
	+ We have regular binary search so our function will look like 2 * log(n) or O(log n)
- More than one change:
	+ We need to perform our union in `else`, which happens twice
	+ In the high level case, we expect DD to be linear or O(n)
- Alternative, not doing DD:
	+ A brute force algorithm would have had to check *all* possible subsets for interesting-ness
	+ The creation of this power set is O($2^n$)

### The "interesting" Function
The big-O's above are assuming our interesting funciton takes constant time. 

Let's assume our linear function's runtime is not constant but monotonic with respect to the number of changes in the input.
+ **monotonic**: the function never gets smaller after it gets bigger, it goes in one direction
	- This means that the runtime for our biggest set is the longest runtime, so we can round everything up to this and we have a constant time
	- This may be a big constant (slow) but it is still a constant in the limit
	- This assumption means that we can treat interesting as constant even if it is not necessarily one 
+ **Note:** if interesting allows unknow answers, our runtime is quadratic, O($n^2$)
	- This is worse, but still significantly better than the brute force alternative
	- *proof left as an exercise to reader*

#### Let's break some of our assumptions of interesting:
+ Not unambiguous: not caused by independent changes
	- Then we may not find the interesting subset
+ Not monotone: If subset is interesting, superset is interesting
	- We will still find interesting but run into runtime problem
	- Answer might not be one-minimal
+ Not consistent: yes or no answer for every subset
	- Some subsets might not build or run
	- We might break bad if sometimes answer is yes and sometimes no 

## Bonus: Other CS Tangents
+ Theory of Computation:
	- Changing deterministic finite automata to undeterministic is A-OK, this is not true if we are working with pushdown automata though
	- This is because of memory, and we do not know how to clone all our memory (in constant amount of time and possibly infinite)

+ Operating Systems/ Virtual Memory:
	- Give every program running the illusion that it is the only program running
	- This gives programs the ability to use the memory addresses they might want/need
	- We can do this with a huge mapping
	- We can also save onto hard drive and give the illusion of infinite memory this way
