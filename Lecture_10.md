#### CS 340 Class Notes Summer 2021
# Lecture 10: Testing   
(mm/dd/2021)


### Review
Test individual pieces of code(fen/class/module)

Test in isolation -> inpits and assert that the output meets some criteria

Modules: Basically made up of classes, 1+. "iport <module>"

Test fixture -> code that runs first to initialize data structures and then afterwards to clean things up


**Advantages**
- test features in isolation (easy to locate bug)
- small (easy to understand)
- fast (fast tests can be run frequently)

### **Test-Driven Development**
- Write unti test for new feature -> fail!
- Write code that unit test code tests
- run all tests
	- Fix anything that breaks 
- Go back t o beginning 


### **Integration Testing**
- Features twork well in isolation 
- What happens if we put unit-tested features together in a larger program?
- Does the program work from start to finish?
	- "end-to-end" testing 
- Combines and tests individual software modules as groups

Whats the difference between unit and integration testing?
- Abstraction! Just one level higher is integration testing

**Ex:** 
- Project 1: Run program with input and diff outputs
- Website/GUI: Use tool to simulate mouse clicks
- As Software: Testing simulate disk/network failure
- Video Game: AI to play the game  

What are some things that are "hard" to test?
- Cost/dependencies/random chance

**Mocking** uses fake/simulated objects (mock objects) that mimic the behavior of the real objects in controlled ways

Stub methods/objects -> place holders for the real thing

Mock Objects are like hte crash test dummies of the coding world

**EX:** 
Web app that uses speach-to-tex API
- API could still be under dev/cost per call
- For each function just return hard-coded data

**EX:**
Code where certain kinds of errors might happen (Disk full, connection dropped) sporatically but "never" in development
- Mocking framework exit to automate this (unittest.mock)
- Saces you time from writting all these wrappers yourself 