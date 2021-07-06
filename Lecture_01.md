#### CS 340 Class Notes Summer 2021
# Lecture 1: What is software engineering?
(05/03/2021)

## Introduction to software engineering

Software is **critical** to modern life. For example:

- Large scale communication and spread of information could not be achieved without software.

- Location based information (i.e. GPS) would be impossible to collect.

- Aggregating a collection of logistics would be difficult, as well.

Other areas include:

- Power -> <a href="https://en.wikipedia.org/wiki/Northeast\_blackout\_of\_2003#Causes">Northeast Blackout of 2003</a>: A \*\*race condition\*\* (an event in which two pieces of code run simultaneously, producing different results depending on the order) caused an alarm system failure, prompting a blackout in the northeastern and north midwestern US, as well as Ontario, Canada.
- Defense -> <a href="https://en.wikipedia.org/wiki/MIM-104\_Patriot#Failure\_at\_Dhahran">Patriot Missile System error</a>: A clock system calculating velocity incorrectly. It was mesuring in tenths of a second, so the devs multiplied that value by ten to get a measurement in seconds. However, they were using a 24-bit register, causing the missile to miss its target by a few hundred meters, killing many people.
- Driving -> <a href="https://en.wikipedia.org/wiki/Sudden\_unintended\_acceleration#Sudden\_acceleration\_in\_Toyota\_vehicles">Bookout v. Toyota Motor Company</a>: A software bug in a few vehicles (including Audi and Toyota) essentially disabled control over acceleration spontaneously, leading to a few fatal crashes.
- Finance/privacy -> <a href="https://en.wikipedia.org/wiki/2017\_Equifax\_data\_breach/a">Equifax data breach</a>: Equifax, a credit reporting institution, was using an outdated version of software called Apache Struts. A security patch was released, but the company's cilents had their privacy breach (i.e. investigation found passwords in standard ASCI text files).
- Health Care -> <a href="https://en.wikipedia.org/wiki/HealthCare.gov#Concerns\_about\_the\_website">HeathCare.gov</a>
- Space -> <a href="https://en.wikipedia.org/wiki/Cluster\_(spacecraft)#Launch\_failure"> ESA Ariane 5, flight 501</a>
- Aviation -> <a href="https://en.wikipedia.org/wiki/Maneuvering\_Characteristics\_Augmentation\_System#Scrutiny">737 Max MCAS</a>
- Medicine -> <a href="https://en.wikipedia.org/wiki/Therac-25#Problem\_description">Therac-25</a>

Many of these software errors can be attributed to poor planning and maintenance of the tools.

### What is going here?

Software is much larger than just a **program**.

A **program** is a collection of instructions or order of operations for a computer to perform a specific task.

**Software** is often a collection of programs, procedures, data, or instructions that work together to provide specific functionality. 

In software engineering, a rather small amount of a team's time is spent actually writing the code. The majority of it is spent on maintenance. FTherefore, a good engineering team needs great...

### ...Management

Design, testing, integration, and documentation are all very important assets for any engineer to provide synergy with team members in a project.