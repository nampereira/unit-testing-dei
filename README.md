# [Software Testing@DEI](https://nampereira.gitbooks.io/software-testing-dei/content/)

This document provides a short introduction to software testing practices that should be employed in programming courses of the Informatics Engineering program at the Computer Engineering Department \(DEI\) from the School of Engineering of the Polytechnic of Porto \(ISEP/IPP\).

Testing is something that every developer does sooner or later. When you write a piece of code, at some point you will execute it and try it out with some test values to see if it runs as you expected. We would like to go a little further. What we are aiming to convey is that tests should be part of your coding activities, and that repeatable and systematic testing will fundamentally make your code more reliable and maintainable.

We will focus on developing basic testing skills, and particularly [**Unit Testing**](#unit-testing). Our approach is a very practical one, in which we aim to get you started with testing as early as possible using Java and its unit testing framework, [JUnit](http://junit.org/junit4/). Software testing can be a broad subject, and it is our understanding that getting started early with software testing practices will make you a better software engineer.

### A Compilation of Existing Materials

This document is a compilation that leverages the vast amounts of good quality content on this subject freely available on the Web. In order to have a single self-contained document, we opted to make verbatim copies of sources and clearly acknowledge them using block quotes as shown below.

> This content is copied verbatim from the source identified at the end of the blockquote.  
> **Source**: \[a reference to the source\]

### GitBook
This document is available as a [**GitBook**](https://nampereira.gitbooks.io/software-testing-dei/content/).

# Testing Levels and Testing Types

> There are generally four recognized levels of tests: **unit testing, integration testing, component interface testing, and system testing.**
>
> **Source**: [https://en.wikipedia.org/wiki/Software\_testing\#Testing\_levels](https://en.wikipedia.org/wiki/Software_testing#Testing_levels)

We will not define all levels of testing, as we are focusing on [**Unit Testing**](#unit-testing).

Testing types include: regression testing, acceptance testing, alpha testing, beta testing, functional vs non-functional testing, usability testing and many more. See: [https://en.wikipedia.org/wiki/Software\_testing\#Testing\_types](https://en.wikipedia.org/wiki/Software_testing#Testing_types)

# Unit Testing

**Unit Tests** can be defined as a piece of code that exercises a very small area of functionality. A typical unit test will test the behavior of a method, but it can test a few methods in a single class, or a small group of related classes. It is preferable to define small units to be tested, as it is easier to test the behavior of a small portion of code.

**Example**: You might write a test to insert a new value to an ordered list and check if the list is still ordered after the insertion.

### **Unit Testing != Integration Testing \(or other levels of test\)**

It is important to distinguish unit tests from other levels of testing. It is particularly common to mistake **unit tests** with **integration tests**.** **Tests that interact with other components \(such as a database\) are integration tests** **and they are beyond the scope of this document. The intuition for this focus is that other levels of testing might not be trivial to automate, and we would like that our tests are easy to automate and be part of our build toolchain \(see [Unit Testing Best Practices](/chapter1.md)\).

It is often necessary to isolate your tests from the behaviour of other classes by using [**mock objects**](https://en.wikipedia.org/wiki/Mock_object)** **and [**stubs**](https://en.wikipedia.org/wiki/Test_stub). For example, when testing code that accesses a database, one can create a class that simulates the database access. This class is part of your test code and allows it to be independent of database configuration, state, etc.

### Why Perform Unit Tests?

> Unit testing will make your life easier. It will make your designs better and drastically reduce the amount of time you spend debugging.
>
> ...\[A developer\] keeps saying things like “that’s impossible” or “I don’t understand how that could happen.”. If you find yourself thinking these sorts of thoughts, then that’s usually a good indication that you don’t have enough confidence in your code—you don’t know for sure what’s working and what’s not. In order to gain \[confidence in your code\], you’ll need to ask the code itself what it is doing, and check that the result is what you expect it to be.
>
> That simple idea describes the heart of unit testing: the single most effective technique to better coding.
>
> **Source**: "Pragmatic Unit Testing in Java with JUnit", Section 1.3 - "Why Should I Bother with Unit Testing?" by Andrew Hunt and David Thomas.

**Next time someone \(maybe a professor, maybe your manager\) asks: **_**Is your code working?**_** You know the right answer is to show your passing tests.**

# Who do I talk to? 

* Ângelo Martins
* António Costa
* Nuno Bettencourt
* Nuno Pereira

# Contents

* [Introduction](README.md)
* [Unit Testing Best Practices](best-practices.md)
* [JUnit Walkthrough](junit-walkthrough.md)
* [Digging Deeper](references.md)


