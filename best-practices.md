# Unit Testing Best Practices

This Section collects a number of best practices for Unit Testing...

### Good Tests FIRST

We will start with the set of practices that are summarized by the acronym F.I.R.S.T: Fast, Independent, Repeatable, Self-checking, and Timely.

> You can avoid many of the pitfalls that unit testers often drop into by following the FIRST principles of unit testing:
>
> * \[F\]ast
>
> * \[I\]solated
>
> * \[R\]epeatable
>
> * \[S\]elf-validating
>
> * \[T\]imely
>
> **Source**: "Pragmatic Unit Testing in Java 8 with JUnit" by Andy Hunt; Dave Thomas; Jeff Langr

##### Fast 
Tests should be easy and quick to execute. The goal is to be able to execute and see the results of the tests automatically without interfering with your coding activities. 
This also means that your tests and the units under test should not have minimal dependencies with external components that might be slower or inaccessible. Minimizing these dependencies relates to the next principle and also aligns well with good object-oriented (OO) design practices.

##### Independent 
Good unit tests focus on a small amount of code to test and do not interact with external components. Using [**mock objects**](https://en.wikipedia.org/wiki/Mock_object)** **and [**stubs**](https://en.wikipedia.org/wiki/Test_stub) to isolate your tests from other classes is often necessary. For example, when testing code that accesses a database, one can create a class that simulates the database access such that our tests can run independent of the existence of a database. 
Your tests should also not rely on preconditions established by other tests so that you are free to select subsets of tests to run and run them in any order. 
 
##### Repeatable
Your tests should not depend on external factors that are not under your control. The result of your tests should be always repeatable.

##### Self-checking
Each test should be able to provide a pass/fail result without having to rely on manual or external checks (which would violate the Independent part of FIRST).

##### Timely
Tests should be written or updated at the same time as the code is developed. Do not procrastinate writing tests for later. Have a look at [Test-driven Development](https://en.wikipedia.org/wiki/Test-driven_development) for a common software practice that advocates writing tests before the actual code.


### JUnit Best Practices

This is a collection of Java and JUnit specific best practices...

[http://www.javaworld.com/article/2076265/testing-debugging/junit-best-practices.html](http://www.javaworld.com/article/2076265/testing-debugging/junit-best-practices.html)

[https://examples.javacodegeeks.com/core-java/junit/junit-best-practices/](https://examples.javacodegeeks.com/core-java/junit/junit-best-practices/)

