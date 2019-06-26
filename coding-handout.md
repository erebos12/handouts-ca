#  Links & Resources

# Table of Contents
1. [Maven-Dependencies](#maven)
2. [Code-Snippets](#snippet)
3. [Links](#links)


<a name="maven"></a>
## Maven-Dependencies

### Hamcrest

     <dependencies>
        <dependency>
            <groupId>org.hamcrest</groupId>
            <artifactId>hamcrest-all</artifactId>
            <version>1.3</version>
            <scope>test</scope>
        </dependency>
     </dependencies>

### Rivescript

     <dependencies>
       ...
        <dependency>
            <groupId>com.rivescript</groupId>
            <artifactId>rivescript-core</artifactId>
            <version>0.10.0</version>
        </dependency>
     </dependencies>

### SpringBoot

    <properties>
        <spring.boot.version>2.1.6.RELEASE</spring.boot.version>
    </properties>

    <parent>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-parent</artifactId>
        <version>2.1.6.RELEASE</version>
        <relativePath/> <!-- lookup parent from repository -->
    </parent>

    <dependencies>
       ...
       <dependency>
           <groupId>org.springframework.boot</groupId>
           <artifactId>spring-boot-starter-web</artifactId>
           <version>${spring.boot.version}</version>
       </dependency>
    </dependencies>


    <build>
        <plugins>
            <plugin>
                <groupId>org.springframework.boot</groupId>
                <artifactId>spring-boot-maven-plugin</artifactId>
            </plugin>
        </plugins>
    </build>

### MockMVC
    <dependencies>
       ...
        <dependency>
            <groupId>io.rest-assured</groupId>
            <artifactId>spring-mock-mvc</artifactId>
            <version>3.3.0</version>
            <scope>test</scope>
        </dependency>
        <dependency>
            <groupId>org.mockito</groupId>
            <artifactId>mockito-core</artifactId>
            <version>2.28.2</version>
            <scope>test</scope>
        </dependency>
        <dependency>
            <groupId>org.mockito</groupId>
            <artifactId>mockito-junit-jupiter</artifactId>
            <version>2.28.2</version>
            <scope>test</scope>
        </dependency>
        <dependency>
            <groupId>org.junit.jupiter</groupId>
            <artifactId>junit-jupiter-engine</artifactId>
            <version>5.3.1</version>
            <scope>test</scope>
        </dependency>
    </dependencies>

    <build>
        <plugins>
            ...
            <plugin>
                <artifactId>maven-surefire-plugin</artifactId>
                <version>2.19.1</version>
                <dependencies>
                    <dependency>
                        <groupId>org.junit.platform</groupId>
                        <artifactId>junit-platform-surefire-provider</artifactId>
                        <version>1.0.1</version>
                    </dependency>
                </dependencies>
            </plugin>
        </plugins>
    </build>


<a name="snippet"></a>
## Code-Snippets

### rivescript

```
! version = 2.0

+ hello bot
- Hello human.

+ my name is *
- <set name=<formal>>Nice to meet you, <get name>.

+ (what is my name|who am i)
- You're <get name>, right?

+ how are you
- I'm fine. Thank you.

+ who is your creator[*]
- I was brought into life by FredAlex.

+ *
- I don't have a reply for that.
- Try asking that a different way.
```


### gitignore

```
.idea
*.iml
target
```

### Dockerfile

```
FROM maven:3.6.1-jdk-11-slim

WORKDIR /code

# Prepare by downloading dependencies
COPY pom.xml /code/pom.xml
RUN ["mvn", "dependency:resolve"]

# Adding source, compile and package into a fat jar
COPY src /code/src
COPY rivescript /code/rivescript


RUN ["mvn", "package"]


EXPOSE 8080
CMD ["/bin/bash", "-c", "java -jar /code/target/ChatBot-1.0-SNAPSHOT.jar"]
```

### Build / Run docker image
```
docker build -t chatbot .
docker run -p 8080:8080 chatbot
```


<a name="links"></a>
## Links

* TIOBE-Index https://www.tiobe.com/tiobe-index/
* Pair-Programming https://en.wikipedia.org/wiki/Pair_programming
* Docker https://docs.docker.com/get-started/
* Rivescript-Playground  https://play.rivescript.com/
* Rivescript (general) https://www.rivescript.com/
* OO-Programming https://medium.freecodecamp.org/object-oriented-programming-concepts-21bb035f7260
* Test-Driven-Development http://agiledata.org/essays/tdd.html
* GIT https://git-scm.com/

### JAVA Links

* SpringBoot https://spring.io/guides/gs/spring-boot/
* Maven https://maven.apache.org/what-is-maven.html
* Hamcrest http://hamcrest.org/