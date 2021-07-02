#### CS 340 Class Notes Summer 2021
# Lecture 19: Debugging as Hypothesis Testing
(06/14/2021)

## **Overview**

* **Bug Localization**
* **One-minimal Sets**
* **Delta Debuggin**


### Bug Localization

What if one commit is huge? Or if the input is too large? Or we have far too many test inputs that generate a given bug?  

We want to. minimize the number of changes that cause a failure.    
(Note: Finding the "Actual" cause of something, as defined in philosophy, is very difficult.) 

### One-Minimal Sets

A **One-minimal set** is a set for which removing any one element makes the set of changes no longer interesting. (Note: a one-minimal set can be interesting with two elements removed, because it is a local minimum for ease of calculation.)

But what does is mean for something to be "interesting"?  
1. Apply changes from set to code
2. Compile w/ changes 
3. Run test
4. If fails, the set is interesting
5. else, the set is not interesting


**Assumptions**  

* Interesting is **Monotonic**: If a subset is interesting, the superset is also interesting. If Interesting(x) = true, then Interesting(x U y) = true. 
*  Interesting is **Unambiguous**: Only one change causes the set to be interesting.
*  Interesting is not caused by independent changes: If Interesting(x) = true and Interesting(y) = true, then Interesting(x U y) = true. 
*  Interesting is **Consistent**: Everything is either interesting or not interesting, and that state does not change. 

### Delta-Debugging

First Attempt:  

```
Minimize_Interesting({c1,c2,c3,c4,....,cn})
	if n = 1: return {c1}
	
	let P1 = {c1, c2, ..., c(n/2)}
	let P2 = {c(n/2 + 1), ..., cn}
	
	if Interesting(P1): return Minimize_Interesting(P1)
	else: return Minimize_Interesting(P2)
	
```

We can't have I(P1) = yes and I(P2) = yes, because Interesting() is unambiguous. 

**BUT**, we can have I(P1) = no and I(P2) = no, because in reality, we are looking for a subset, not a single element. 

So, we take all the elements of P1, and find the minimal elements from P2 to add. 

Then, we take all the elements of P2, and find the minimal elements from P1 to add. 

The union of the minimal elements from P1 and P2 will be our one-minimal set. 

Second Attempt (Delta-Debugging):

```
DD({c1, c2, ...,cn}, required = {})
	if n = 1:
		return {c1}
	let P1 = {c1, ..., c(n/2)}
	let P2 = {c(n/2 + 1), ..., cn}
	
	if Interesting(required U P1) = yes:
		return DD(P1, required)
	elif Interesting(required U P2) = yes:
		return DD(P2, required)
	else:
		return DD(P1, required U P2) U DD(P2, required U P1)
```































