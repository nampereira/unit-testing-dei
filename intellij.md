# Setup Unit Tests Using IntelliJ IDEA

This Section provides some details about setting up a project with IntelliJ IDEA. We will create a new Maven project from archetype "quickstart" in IntelliJ.

### Create a Project

Start by creating a new project in **File**-&gt;**New Projec**t. In the folowing dialog, select **Maven** and then **org.apache.maven.archetypes:maven-archetype-quickstart**. Click **Next**. This will take you to the following dialog, where you can enter the GroupId \(e.g. **pt.dei.junit\_example**\), ArtifactId \(e.g. **JunitExample**\) and Version \(e.g. 1.0-SNAPSHOT\). Proceed with **Next**. ![](/assets/intellij-maven-project2.png)You can leave the default values in the following dialog and click **Next**.![](/assets/intellij-maven-project3.png)Finally, enter the project name \(e.g. JUnitExample\) and **Finish**.![](/assets/intellij-maven-project4.png)You might see a message \(shown bellow\) asking to import the Maven Project. Select **Enable Auto-Import**.![](/assets/intellij-maven-project5.png)This will generate your Project with a folder with the same name as the artifactId given \(**JUnitExample** in this case\). Under this folder, you will have to create a [standard project structure](/%28https://maven.apache.org/guides/introduction/introduction-to-the-standard-directory-layout.html).

Start by creating the directory structure for the application main code.To do this, right click on the main project folder \(here, **JUnitExample**\) and select New-&gt;Directory.

![](/assets/intellij-maven-project6.png)

You can enter the full path for the application main code folder. The path starts with **src/main/java **and then set it according to the GroupId entered previously \(in our example, **pt.dei.junit\_example**, so we enter** src/main/java/pt/dei/junit-example**\). ![](/assets/intellij-maven-project7.png)Next, create the directory structure for the test code **under the src** folder** **\(in our example, we enter **test/main/java/pt/dei/junit-example**\).![](/assets/intellij-maven-project8.png)You should now have a [standard project structure](/%28https://maven.apache.org/guides/introduction/introduction-to-the-standard-directory-layout.html) similar to the following one.

![](/assets/intellij-maven-project9.png)

Now we need to define where are our code and test source folders. Open the project structure settings under **File**-&gt;**Project Structure**. Select the **src/main** folder and set it as the **source folder**. Do this by right clicking the **src/main **folder and selecting the option **Source.**

![](/assets/intellij-maven-project10.png)

Finally, set the **src/test** as the **test source folder **\(right click **src/test** and select **Tests**\). You should end with a project structure dialog similar to the following.

### ![](/assets/intellij-maven-project11.png)

You have now a Maven project in IntelliJ. All you need to do is to configure JUnit as a dependency using Maven. The next section shows how to do this.

### The Project Object Model \(POM\)

The pom.xml file is the core of a project's configuration in Maven. A POM file can have a lot of information, and you don't need to understand all of it for now. As an example, the POM created for this project was as follows.

```XML
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>

    <groupId>pt.dei.junit-example</groupId>
    <artifactId>JUnitExample</artifactId>
    <version>1.0-SNAPSHOT</version>
</project>
```

Let us add JUnit as a dependency of the project by adding a dependency section. If your POM file looks different from the above \(it might already have a **dependencies** section of even JUnit as a dependency\), just try to make it look similar to the following.

```XML
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>

    <groupId>pt.dei.junit-example</groupId>
    <artifactId>JUnitExample</artifactId>
    <version>1.0-SNAPSHOT</version>

    <!-- Start of dependencies section -->
    <dependencies> 

        <!-- Declare JUnit as a dependency -->
        <dependency>
            <groupId>junit</groupId>
            <artifactId>junit</artifactId>
            <version>4.12</version>
            <scope>test</scope>
        </dependency>

    </dependencies>

</project>
```

Now all you need to do is to add some tests and code to your project!

