# Setup Unit Tests Using Maven

This Section provides some details about setting up a project with JUnit using Maven. It is inspired by [Maven in 5 Minutes](https://maven.apache.org/guides/getting-started/maven-in-five-minutes.html).

### Install Maven

1. You will need to have [Java](http://www.oracle.com/technetwork/java/javase/downloads/index.html) installed.
2. [Download Maven](https://maven.apache.org/download.html) and follow the [installation instructions](https://maven.apache.org/download.html#Installation). 

Now you should have Maven installed. Check it with:
```
mvn --version
```

You should be ready to go. In any case, you can always check the [Guide to Configuring Maven](https://maven.apache.org/guides/mini/guide-configuring-maven.html).

### Create a Project

Create a directory where you want your new project to reside and start a command line in that directory. Now we can generate a new Maven project using the archetype "quickstart":
```
mvn archetype:generate -DgroupId=pt.dei.junit_example -DartifactId=JUnitExample -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false
```

This will generate a folder with the same name as the artifactId given (*JUnitExample* in this case). Under this folder, you will have the following [standard project structure](https://maven.apache.org/guides/introduction/introduction-to-the-standard-directory-layout.html).
```
JUnitExample
|-- pom.xml
`-- src
    |-- main
    |   `-- java
    |       `-- pt
    |           `-- dei
    |               `-- junit_example
    |                   `-- App.java
    `-- test
        `-- java
            `-- pt
                `-- dei
                    `-- junit_example
                        `-- AppTest.java
```                        

The ```src/main/java``` directory contains the project source code, the ```src/test/java``` directory contains the test source, and the ```pom.xml``` file is the project's Project Object Model, or POM.

### The Project Object Model (POM)

The pom.xml file is the core of a project's configuration in Maven. A POM file can have a lot of information, and you don't need to understand all of it for now. As an example, the POM created for this project was as follows.
```XML
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/maven-v4_0_0.xsd">
  <modelVersion>4.0.0</modelVersion>
  <groupId>pt.dei.junit_example</groupId>
  <artifactId>JUnitExample</artifactId>
  <packaging>jar</packaging>
  <version>1.0-SNAPSHOT</version>
  <name>JUnitExample</name>
  <url>http://maven.apache.org</url>
  <dependencies>
    <dependency>
      <groupId>junit</groupId>
      <artifactId>junit</artifactId>
      <version>3.8.1</version>
      <scope>test</scope>
    </dependency>
  </dependencies>
</project>
``` 
You will notice that JUnit is mentioned there (the version number might vary), inside a dependencies section. That means Maven already defined JUnit as a dependency and will take care of setting it up for us.

If you have a JUnit version earlier than 4 (as we have above - 3.8.1), go ahead and update it to version 4.12. The resulting POM is below.
```XML
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/maven-v4_0_0.xsd">
  <modelVersion>4.0.0</modelVersion>
  <groupId>pt.dei.junit_example</groupId>
  <artifactId>JUnitExample</artifactId>
  <packaging>jar</packaging>
  <version>1.0-SNAPSHOT</version>
  <name>JUnitExample</name>
  <url>http://maven.apache.org</url>
  <dependencies>
    <dependency>
      <groupId>junit</groupId>
      <artifactId>junit</artifactId>
      <version>4.12</version>
      <scope>test</scope>
    </dependency>
  </dependencies>
</project>
``` 

### Build the Project

You can now build the project:
```
mvn package
```

This should terminate successfully. If the project already included unit tests, they would be run as this is one of the steps executed with the above. If you want to run the tests only, run:
```
mvn test
```

Now all you need to do is to add some tests and code to your project!
