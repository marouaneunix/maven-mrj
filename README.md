## Goals:

    - clean (delete target dir)
    - compile (compile the source code (classes, ...) on target)
    - package (compile + package.[jar/war] 
    - install (package + copy to maven local repo)
    - deploy (install remotely)

## Dependency
    - version
    - types
    - scopes
    - transitive dependencies

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