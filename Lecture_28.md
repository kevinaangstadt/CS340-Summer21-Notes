#### CS 340 Class Notes Summer 2021
# Lecture 28: Ethics in Software Development  
(07/05/2021)

## Ethics in Software Engineering

**Ethics**
: seeks to resolve questions of human morality by defining various concepts
- good vs. evil
- right and wrong
- virtue and vice
- justice and crime

Basically... everything involving "should"
- Actions you can take that are ethical
    - codes of conduct
- Software itself and its impact on society

**Questions About the Software We Write**
- what types of harm can the public suffer?
- How do SEs contribute good/harm?
- How can we practice "good" SE?
- What professional codes do we follow?

**Ex of things we might consider:**
- Security
- Privacy
- Accessability
- Freedom
    - Traditionally communities are willing to give up somw freedom (to a public gov.) in exchange for basic guarentees
        - safety
        - protection
        - the good of others
    - SW: Private companies vs. Gov't

## Q: Who Could Be Harmed By Our Code?

**Stakeholder**
: Anyone impacted by the software or your actions as a developerof the software
- customers
- chain of customers
    - customers of our customers
    - ...
    - turtles all the way down
- us
- other developers
- testers/QA
- manegement
- shareholders

### Case Study 1

College deposite system -> but the college says that the payment failed (insufficient funds)

Bank -> well everything was fine
    - enough money in the account
    - money is now missing from the account and we dont know where it went
    - open investigation -> take months and you wont get $ back until the investigation finishes

College -> need money by tomorrow or the student can't start

**Stakeholders:**
- Student
- College
    - SW deposites
    - money
- Bank
    - SW money transfers
- Guardians
    - whoever paid

**Who Is at Fault?**
- College or Bank

**Who Is Resposible For Resolving?**
- FDIC

### Case Study 2

Allegheny County Office of Children, Youthm abd Families (PA) algorithmic prediction of child abuse risk

**What Issues Could Happen?**
- Privacy: people could premptively be labeled as child abusers despite not doing anything
- Could label certain communities more than others (this happened)
    - mostly predicted abuse in lower income families

**Why Did This Happen?**
- Biased data
    - not representative
    - have too much of something not enough of everything else
- Why was the data biased?
    - sampling bias
    - past data is mostly about lower income community
        - court records -> pred. lower income
        - public health/mental health -> pred. lower income

### Case Study 3

You work for a startup designing SW to moniter network traffic -> looking for illegal activity (copywrited downloads/spam/phishing)
- you overhear your supervisor talking about a new client -> country know for human rights abuses

**It can be very easy to detatch when we dont know the stakeholders**




Text-body 
...  
...  
...  
...  
...  
put two spaces for clean line breaks

```python
python example code(foo)
	Statement
	statement
```

Explanations of things.  
...  
...  
...  
...  

- Bulleted Points
	+ With more details

**Maybe important detail**

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