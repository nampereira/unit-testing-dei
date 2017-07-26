# Introduction

While you can test write all the code necessary for your tests, it is common to use a testing framework that helps with the common tasks and allows the developer to write tests faster and execute them automatically. Table 1 provides a summary of how the typical unit testing framework can help the developer.

> **Table 1** How unit-testing frameworks help developers write and execute tests, and review results
>
> | Unit-testing practice | How the framework helps |
> | :--- | :--- |
> | Write tests easily and in a structured manner. | Framework supplies the developer with a class library that holds: \(i\) base classes or interfaces to inherit; \(ii\) attributes to place in your code to note your tests to run; \(ii\) assert classes that have special assert methods you invoke to verify your code. |
> | Execute one or all of the unit tests. | Framework provides a test runner \(a console or GUI tool\) that: \(i\) identifies tests in your code; \(ii\) runs tests automatically; \(iii\) indicates status while running; \(iv\) can be automated by command line. |
> | Review the results of the test runs. | The test-runners will usually provide information such as: \(i\) how many tests ran/didn’t run/failed; \(ii\) the result of each test \(iii\) the ASSERT message you wrote; \(iv\) the code location that failed; \(v\) possibly a full stack trace of any exceptions that caused the test to fail. |
>
> **Source**: "The Art of Unit Testing with Examples in .NET" by Roy Osherove

In this Section, we will perform a practical Walkthrough of using using **Java** and its unit testing framework, [**JUnit**](http://junit.org/junit4/).

# Preliminaries

Before starting, let us briefly provide some pointers on how to setup your environment and a little guidance about naming conventions.

### Setup

IDEs such as Eclipse, NetBeans or IntelliJ have support to run JUnit tests and, ofcourse, you can always tun them from the command line. Here are a few pointers on how to setup the support for JUnit in the different IDEs.

##### **IntelliJ IDEA**

After creating a new Java project in IntelliJ, you will have to go trough a few steps to configure the test libraries, create the tests, and run/debug configurations. Have a look at the [IntelliJ Testing Online Support](https://www.jetbrains.com/help/idea/2016.3/testing.html).

##### Eclipse

After creating a new Java project, create a new folder for your tests, and then add "JUnit 4 test cases". Have a look at the [Eclipse Writing and Running JUnit tests](http://help.eclipse.org/neon/topic/org.eclipse.jdt.doc.user/gettingStarted/qs-junit.htm).

##### NetBeans

After creating a new Java project, you can add new JUnit Test classes . Have a look at [Writing JUnit Tests in NetBeans IDE](https://netbeans.org/kb/docs/java/junit-intro.html).

### Naming Conventions

We use common conventions when naming our test classes and methods.

The test class should be named after the unit under test with "Test" appended at the end. For example, if we are testing a class named **Person**, the test class will be named **PersonTest**.

As for the test methods, we will use descriptive names in the form: _whenDoingSomeBehaviorThenSomeResultOccurs_. Some examples of test cases for an ATM in Table 2.

| Test Description | Test Method Name |
| :--- | :--- |
| Check if balance is reduced correctly when performing a single withdrawal.  | WhenWithdrawalThenReduceBalanceByWithdrawnAmount |
| Check if attempt to withdraw more than current balance generates error. | WhenWithdrawalMoreThenAvailableFundsThenGenerateError |
| Check if balance is correctly updated after multiple deposits. | WhenMultipleDepositsThenIncreaseBalanceBySumOfDeposits |

Yes, these are quite long! There are many schools of though on the issue of [naming conventions for unit tests](https://dzone.com/articles/7-popular-unit-test-naming), and you might prefer some other naming convention. What is important is to choose one and keep it consistent.



---

Major refs:

[https://www.toptal.com/java/getting-started-with-junit](https://www.toptal.com/java/getting-started-with-junit)

[http://www.codeaffine.com/2014/09/24/junit-nutshell-junit-tutorial/](http://www.codeaffine.com/2014/09/24/junit-nutshell-junit-tutorial/)

