## Introduction ##

This project is a JPEG 2000 encoder/decoder written in pure Java.  Its goal is to be a reference implementation of (at least) part 1 of the JPEG 2000 specification.

The code here originally came from version 5.1 of JJ2000 as downloaded from this website: http://jpeg2000.epfl.ch/.  However, that code is incomplete, has bugs, has performance issues, and has memory-usage issues.  So a Google Code project was created so that modifications and improvements could be made.

## Building ##

Currently this project has project files for [Ant](http://ant.apache.org/) and for [Maven](http://maven.apache.org/).  For either one, we assume the following:
  * You have some flavor of JDK already installed on your computer.
  * You have the `JAVA_HOME` environment variable set to the root directory of your JDK.
  * `JAVA_HOME\bin` is in your `PATH` (i.e. so that typing `javac` from a command line succeeds).

### Ant ###

  * Download and install [Ant](http://ant.apache.org/) as described on their web page.  (Basically, this amounts to unzipping the Ant distribution somewhere and adding Ant's `bin` directory to your `PATH`.)
  * Check out the source code for this project.  (See [here](http://code.google.com/p/jj2000/source/checkout).)
  * In a command prompt, issue the command `ant` from the same directory as the file `build.xml`.  If everything goes well, you should have a freshly compiled jar in the `target` subdirectory.

### Maven ###

  * Download and install [Maven](http://maven.apache.org/) as described on their web page [here](http://maven.apache.org/download.html#Installation).  (Basically, this amounts to unzipping the Maven distribution, setting the `M2_HOME` environment variable, and putting `M2_HOME\bin` in your `PATH`.)
  * Check out the source code for this project.  (See [here](http://code.google.com/p/jj2000/source/checkout).)
  * In a command prompt, issue the command `mvn install` from the same directory as the file `pom.xml`.  If everything goes well, you should have a freshly compiled jar in the `target` subdirectory.

To use the new jar in your other Maven projects, you can now add this dependency to those projects' `pom.xml` files:
```
<dependency>
    <groupId>jpeg2000.epfl.ch</groupId>
    <artifactId>jj2000</artifactId>
    <version>5.2-SNAPSHOT</version>
</dependency>
```

### Eclipse ###

Maven has the ability to automatically generate Eclipse project files.  If this is the first time you've used Maven in a given Eclipse workspace, then (only once for this workspace) you must issue the following command:

```
mvn -Dworkspace=PATH_TO_WORKSPACE eclipse:configure-workspace
```

Replace `PATH_TO_WORKSPACE` with the path to your Eclipse workspace.  This sets up Eclipse to know where Maven puts its compiled jars.

Now to generate an Eclipse project, issue the following command:

```
mvn eclipse:eclipse
```

Then start up your Eclipse, import an existing project, select the directory where `pom.xml` lives, and select the newly generated project.