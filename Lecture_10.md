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