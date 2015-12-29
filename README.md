api-parent-pom
==============

<a href="https://raw.githubusercontent.com/groupon/api-parent-pom/master/LICENSE">
    <img src="https://img.shields.io/hexpm/l/plug.svg"
         alt="License: Apache 2">
</a>
<a href="http://search.maven.org/#search%7Cga%7C1%7Cg%3A%22com.groupon.api%22%20a%3A%22api-parent-pom%22">
    <img src="https://img.shields.io/maven-central/v/com.groupon.api/api-parent-pom.svg"
         alt="Maven Artifact">
</a>

Standardized set of build tool configurations for Groupon API projects.

Motivation
-----

As the number of Groupon API projects has grown and our code/build standards have matured.  We required a better way to share configuration across projects rather than replicate the same configuration (e.g. compiler, checkstyle, findbugs, etc.) across all of our projects.  The parent pom is intended to only provide the base configuration for plugins that we expect to be consistent throughout projects. Project specific configuration and plugins should not be included in the parent pom.

Usage
-----

Determine the latest version of the api parent pom in [Maven Central](http://search.maven.org/#search%7Cga%7C1%7Cg%3A%22com.groupon.api%22%20a%3A%22api-parent-pom%22).

Set the __parent__ block in your pom:

```xml
<parent>
    <groupId>com.groupon.api</groupId>
    <artifactId>api-parent-pom</artifactId>
    <version>VERSION</version>
    <relativePath />
</parent>
```

Next, enable the desired plugins from the parent pom's __pluginManagement__ block in the __plugins__ block; for example to use the javadoc plugin specified in the parent include the following:

```xml
<build>
    <plugins>
        <plugin>
            <groupId>org.apache.maven.plugins</groupId>
            <artifactId>maven-javadoc-plugin</artifactId>
        </plugin>
    </plugins>
</build>
```

Building
--------

Prerequisites:
* [JDK8](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)
* [Maven 3.3.3+](http://maven.apache.org/download.cgi)

Building:

    api-parent-pom> mvn verify

To use the local version you must first install it locally:

    api-parent-pom> mvn install

You can determine the version of the local build from the pom file.  Using the local version is intended only for testing or development.

License
-------

Published under Apache Software License 2.0, see LICENSE

&copy; Groupon Inc., 2015
