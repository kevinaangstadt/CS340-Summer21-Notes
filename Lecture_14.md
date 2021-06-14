# Lecture 14 (06-02)

## Quality Assurance Wrap-Up:
- Gaining confidence in specifications / no bugs / bad behavior.
- Maintainance of desired levels of quality

Internal quality -> developer-facing (readable / maintainable)
External quality -> customer-facing (does it work as promised?)
- Why do we care?
	- External: 
		- To retain loyal customers!
	- Internal: 
		- Reduction in duplication of effort
		- Time == money
		- Maintainance is our biggest cost (70%=90%)
		- [Amdahl's Law](https://en.wikipedia.org/wiki/Amdahl%27s_law)


### How do we measure quality?
- Testing! -> potentially millions of lines of code
- Human Review! -> Theory doesn't "scale" well between size of code and time
	- Limits on what we can decide
- Quality of tests:
	- **Internal**: Code coverage (lines, paths, branches, modified condition decision coverage (high-assurance software)). Coverage evalutates multiple options which are *relative comparisons, not absolutes*. Internal coverage also leads towards **mutation testing**, which creates altered copies of a program, asking whether the program will notice?
		- Measuring test quality can be obnoxious and tedious, so it's best to automate test writing. This requires:
			- Inputs: 
				- random inputs
				- common parameters
				- computing path predictions.
			- Oracle: 
				- If we manually make our inputs, we can manually create ouptuts
				- Learning invariants (conditions which are always true)
					- Running the code to see what is always true
					- Using mutation testing to rule out superfluous invariants
	- **External** -> Internal Quality => External quality
		- Alpha / Beta testing
			- Gaining knowledge through "samples" of many user inputs.
			- This can involve distributing multiple versions of a program to different users and comparing. 
			
	#### Kinds of internal testing:
	- Regression tests -> checking to see if the old bugs show up again
	- Unit testing -> testing individual pieces of code in isolation
	- Integration testing -> do pieces of code combine and still function correctly?
	- End to end testing (as featured in P1) -> essentially testing a program from beginning to end