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
> #### Fast
>
> The dividing line between fast and slow unit tests is somewhat arbitrary—as Justice Potter Stewart said, “I know it when I see it.” Fast tests deal solely in code and take a few milliseconds at most to execute. Slow tests interact with code that must handle external evil necessities such as databases, files, and network calls. They take dozens, hundreds, or thousands of milliseconds.
>
> ...
>
> Your unit tests will run faster, and you’ll find them easier to write, if you seek to minimize the amount of code that ultimately depends on slow things. Minimizing such dependencies is also a goal of good design—again and again, as here, you’ll find that unit testing gets easier the more you’re willing to align your code with clean object-oriented \(OO\) design concepts.
>
> #### Isolated
>
> Good unit tests focus on a small chunk of code to verify. That’s in line with our definition of unit. The more code that your test interacts with, directly or indirectly, the more things are likely to go awry.
>
> The code you’re testing might interact with other code that reads from a database. Data dependencies create a whole host of problems. Tests that must ultimately depend on a database require you to ensure that the database has the right data. If your data source is shared, you have to worry about external changes \(maybe out of your control\) breaking your tests. Don’t forget that other developers are often running their tests at the same time! Simply interacting with an external store increases the likelihood that your test will fail for availability or accessibility reasons.
>
> Good unit tests also don’t depend on other unit tests \(or test cases within the same test method\). You might think you’re speeding up your tests by carefully crafting their order so that several tests can reuse some of the same expensively constructed data. But you’re simultaneously creating an evil chain of dependencies. When things go wrong—and they will—you’ll spend piles of time figuring out which one thing buried in a long chain of prior events caused your test to fail.
>
> ...
>
> The Single Responsibility Principle \(SRP\) of OO class design says that classes should be small and single-purpose. More specifically, the SRP says your classes should have only one reason to change.
>
> The SRP provides a great guideline for your test methods, also. If one of your test methods can break for more than one reason, consider splitting it into separate tests. When a focused unit test breaks, it’s usually obvious why.
>
> Your tests want to each be like Switzerland! Keep ‘em isolated and running like clockwork!
>
> #### **Repeatable**
>
> A repeatable test is one that produces the same results each time you run it. To accomplish repeatable tests, you mustisolatethem from anything in the external environment not under your direct control.
>
> ...
>
> Without repeatability, you might be in for some surprises at the worst possible moments. What’s worse, these sort of surprises are usually bogus—it’s not really a bug, it’s just a problem with the test. You can’t afford to waste time chasing down phantom problems.
>
> #### Self-Validating
>
> ...
>
> Tests aren’t tests unless they assert that things went as expected. You write unit tests to save you time, not take more of your time. Manually verifying the results of tests is a time-consuming process that can also introduce more risk—it’s easy to get dozy and gloss over important signs when you pore over the voluminous output that pseudotests can produce.
>
> Not only must your tests be self-validating, but they must also be self-arranging. Make sure you don’t do anything silly, such as designing a test to require manual arrange steps before you can run it. You must automate any setup your test requires. Remember, regardless: requiring external setup in order to a run a test violates the \[I\]solated part of FIRST.
>
> ...
>
> #### Timely
>
> You can write unit tests at virtually any time. You could dredge up code in any old portion of your system and start tacking on unit tests to it. But you’re better off focusing on writing unit tests in a timely fashion.
>
> Unit testing is a good habit. With most good habits that you’ve not yet completely ingrained, such as brushing your teeth, it’s easy to procrastinate and make excuses why you can skip the practice “just this once.” Your dentist might love your funding his or her practice, but you’re going to hate the time it takes to scrape away the tartar that’s built up.
>
> Likewise, the more you defer probing at your code with unit tests, the more plaque buildup \(cruft\) and cavities \(defects\) you’ll need to deal with. Also, once you check code into your source repository, chances are low that you’ll find the time to come back and write tests.
>
> Many test-infected dev teams have guidelines or strict rules around unit testing. Some use review processes or even automated tools to reject code without sufficient tests.
>
> ...
>
> **Source**: "Pragmatic Unit Testing in Java 8 with JUnit" by Andy Hunt; Dave Thomas; Jeff Langr

### JUnit Best Practices

This is a collection of Java and JUnit specific best practices...

[http://www.javaworld.com/article/2076265/testing-debugging/junit-best-practices.html](http://www.javaworld.com/article/2076265/testing-debugging/junit-best-practices.html)

[https://examples.javacodegeeks.com/core-java/junit/junit-best-practices/](https://examples.javacodegeeks.com/core-java/junit/junit-best-practices/)

