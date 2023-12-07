<img src="https://github.com/hhanae/docker-demo-lab/assets/97336261/863ae84e-5c9f-43fd-8538-f7ed51902268" width="200">
<h1 align="center">
  Containerization Microservices Lab Demo
  <br>
</h1>

<h4 align="center">Welcome to the Docker Example Project! This project is designed to help you understand the basic concepts of containerization using <a href="(https://www.docker.com/)" target="_blank">Docker . architecture</a> in computer science.</h4>

![Uploading 1_1P9HOcZJSa9HPm6nuslqdA (2).gif…]()



<p align="center">
  <a href="#why-to-containerize">Why To Containerize ?</a> •
  <a href="#prerequisites">Prerequisites</a> •
  <a href="#steps">Steps</a> 
</p>



## Why To Containerize

Containerization offers advantages in terms of consistency, portability, scalability, and resource efficiency. These benefits make containers a valuable technology for modernizing application development and deployment workflows.


## Prerequisites

Before you begin, ensure you have the following installed:

* Docker

## Project Structure

These are the important files in our lab project:

> Dockerfile:

Defines the instructions for building the Docker image.

> src/:

Contains the application source code.

> docker-compose.yml (if used):

Defines services, networks, and volumes.


## Steps

Before you start, if you havn't create your microservices project yet, you can download or clone <a href="(https://www.docker.com/](https://github.com/hhanae/microservices_demo/tree/main)" target="_blank">our's to get started!

### Step 1: Generate the jars:

First, we have to generate the jars of each project by running the command below in each service:

```bash
mvn package
```

> We use mvn command because we are working with maven. If you are working with gradle, you have to use this command:

```bash
./gradlew build
```

Before we continue, be sure the jar was generated in the target folder:

![image](https://github.com/hhanae/microservices_demo/assets/97336261/dde949a1-8a3e-4705-8b15-91a090c872c6)

> You can also test if the jar is working correctly in local before you continue by using this command:

```bash
java -jar build/libs/<the-project-name>-<x.x.x>-SNAPSHOT.jar
```

### Step 1: Creating the Dockerfiles:

Second, we create a dockerfile in each project and we add its associated jar:
```bash
FROM openjdk:17-jdk-slim

ARG JAR_FILE=target/<the-project-name>-<x.x.x>-SNAPSHOT.jar
COPY ${JAR_FILE} <the-project-name>-<x.x.x>-SNAPSHOT.jar

EXPOSE 8089

ENTRYPOINT ["java", "-jar", "/<the-project-name>-<x.x.x>.jar"]
```


> [@hanim_hanae]([https://twitter.com/amit_merchant](https://hanim-hanae.vercel.app/)https://hanim-hanae.vercel.app/)

