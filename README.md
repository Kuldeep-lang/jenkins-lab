# Jenkins CI with Maven

A Java application that **Jenkins** builds automatically with **Maven** whenever code is pushed to this repository.

| File | Purpose |
|---|---|
| `src/HelloWorld.java` | The Java application |
| `pom.xml` | Maven build file: compiles for Java 17 and packages a runnable jar |

## How the CI works

1. A push to `main` sends a GitHub webhook to Jenkins (`http://<jenkins-server>:8080/github-webhook/`).
2. Jenkins pulls the latest code.
3. Jenkins runs `mvn clean package`, which compiles the code and builds `target/jenkins-lab-1.0.jar`.
4. Jenkins runs the jar and shows the build status (`BUILD SUCCESS`).

## Build locally

```bash
mvn clean package
java -jar target/jenkins-lab-1.0.jar
```
