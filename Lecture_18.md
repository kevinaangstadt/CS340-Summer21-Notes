# Lecture 18 (06-11)

## Our plan (from the previous class):
- Run both passing and failing tests
- Mark down the lines that are executed for each
- Do "math" to rank lines by this coverage information
	- Demote lines that are used to pass memory tests
	- Prioritize lines that are used just in failing tests
- **What* is* the math that we're going to use? There are two main approaches here:**
	- **Tarantula**: *S(L) = (failed(L) / total failed) / ((failed(L) / total failed) + (passed(L) / total passed)), where S is the suspicion of line L*.
	- **Ochiai Metric**: *S(L) = failed(L) /  $\sqrt{failed(L) (failed(L) + passed(L))}$*
	- The better metric here will put the "actual" bugged line as a priority.

## Implementing these debugging methods
```python
def sus_score(self , line):

	"""
	Computes Ochiai suspiciousness score of a given line
	line: line number to provide a suspiciousness metric for
	"""
	# number of times the line was used for passing and failing tests
	p = self.passed\_lines\[line\]
	f = self.failed\_lines\[line\]

	# denom will be 0 if we \*\*never\*\* cover this line
	denom = (math.sqrt(self.totalfailed \* (f + p)))

	if denom == 0:
		return None
	else:
		return (f)/denom

def passed(self, executable, missed):

	"""
	Test cased passed... log coverage for the given executable lines and missed lines
	"""
	self.totalpassed += 1
	self.\_add\_to\_dict(self.passed\_lines, executable, missed)

def failed(self, executable, missed):
	"""
	Test cased passed... log coverage for the given executable lines and missed lines
	"""
	self.totalfailed += 1

	self.\_add\_to\_dict(self.failed\_lines, executable, missed)
```


## What are the pieces of a bug report?
- Steps to reproduce
	- We want the steps and inputs to be minimized
	- Automation is useful for this task

**Can we automate this task of minimizing inputs?**
- Ex. Firefox prints crashes. Can we make a smaller HTML file that will cause crashes?

**Another problem of minimization**
- Yesterday, the code "worked". Today, the code "crashed". Which commit caused this to fail?
- A **causality** is influenced by which one event (a cause) contributes to the production of another event (an effect) where the cause is partly responsible for the effect, and the effect partly depends on the cause
	- Counterfactual theories on causality: *If A had not occurred, then C would not have occurred*
- One can conduct a binary search upon a repo's history to find the failure-inducing commit. This takes O(ln(n)) time, where n = number of commits. This is called **bisecting**

**Useful bisecting commands:**
`git bisect start`: start a bisecting search
`git bisect goood`: mark a commit as "good"
`git bisect bad`: mark a commit as "bad"
`git bisect reset`: get out of a bisecting search
`git bisect run`: run a script to automate the search (requires a good and bad mark)