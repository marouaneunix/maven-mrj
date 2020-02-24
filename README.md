## Goals:

    - clean (delete target dir)
    - compile (compile the source code (classes, ...) on target)
    - package (compile + package.[jar/war] 
    - install (package + copy to maven local repo)
    - deploy (install remotely)

## Build:

Override default config

### example:
override the  default package name:

    <build>
        <finalName>foo</filename>
    </build>

## Dependencies

List what you need

3 items required: groupId, artifactId, version

### example:
    
    <dependencies>
        <dependency>
            <groupId>org.apache.commons</groupId>
            <artifactId>commons-lang3</artifactId>
            <version>3.7</version>
        </dependency>
    </dependencies>

## Versions:
SNAPSHOT: Incremental version, the Maven considers it the "as-yet-unreleased" version of the
associated MajorVersion, MinorVersion, or IncrementalVersion.

Release:

## Packaging Types

    pom, jar, war, ear, maven-plugin
    <packaging>jar</packaging>
default : jar

## Transitive Dependencies

If you add a dependency, Transitive dependencies are downloaded
### Example
    if dependency is : hibernate-core
    then transitive dependencies are: antir, jaxb-api, stax-ex, txw2, ...

##Scopes
Is used to specify the visibility of a dependency, relative to the diff lifecycle phases (build, test, runtime etc)

    - compile : maven default scope. Dependencies with compile scope are needed to build, test, and run the project. Scope compile is to be required in most of the cases to resolve the import statements into your java classes sourcecode.
    - provided : is used during build and test the project.
    - runtime : are not needed to build, but are part of the classpath to test and run the project.
    - test: are not needed to build and run the project, They are needed to compile and run the unit tests. 
    - system (never use)
    - import

## 5- Repositories

### Local Repository
    maven storage: ~/.m2
    storage path : ~/.m2/repository/<groupId>/<artifactId>
### Remote Repository
    default location: repo.maven.apache.org
    config : settings.xml
#### Example
```
<repositories>
    <repository>
        <id>spring-snapshot</id>
        <name>Spring Maven SNAPSHOT Repository</name>
        <ur>http://repo....</url>
        <snapshots>
            <enabled>true</enabled>
        </snapshots>
        <releases>
            <enables>false</enabled>
        </releases>
    </repository>
</repositories>
```

## 6- Plugins
    Goals == plugins (clean, deploy...)
```
<plugin>
    <artifactId>maven-clean-plugin</artifactId>
    <version>3.1.0</version>
    <executions>
        <execution>
            <id>clean</id>
            ....
        </execution>
    </executions>
</plugin>
```
### Phases
    - validate: validate project and structure
    - compile:
    - test
    - package
    - integration-test: deploy and run integration tests
    - verify
    - install
    - deploy
### Compiler Plugin
    Invokes javac, Default older (1.5), Configuration, fork, memory, source/target
### Jar Plugin

### Source Plugin

### Javadoc Plugin
