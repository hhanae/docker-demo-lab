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
FROM openjdk:19-alpine
COPY target/<the-project-name>-<x.x.x>.jar
ENTRYPOINT ["java", "-jar", "/<the-project-name>.jar"]
```
### Step 2: Creating the Docker Compose File:
We create a "docker-compose.yml" file in the top level of our projects and we add the necessary configuration: version, services, volumes and networks.

### Step 3: Running the docker-compose.yml :
We run thedocker-compose to build the necessary images, create the containers, and start them.
![image](https://github.com/hhanae/docker-demo-lab/assets/97336261/e380c8cb-1a5e-4e49-b72b-0de97f059af3)

To make sure all the Containers are running Correctly, we navigate to the Eureka_Server page to make sure all the microservices are present.
![image](https://github.com/hhanae/docker-demo-lab/assets/97336261/657f2f8d-7839-44d6-b5cf-d165d8913bbf)

We can also browse to the Clients microservice:
![image](https://github.com/hhanae/docker-demo-lab/assets/97336261/40a335c8-6d21-4ee8-86ce-7c2d2caabd52)

Or, to the Voitures microservice:
![image](https://github.com/hhanae/docker-demo-lab/assets/97336261/9d39ad10-13d6-4307-b217-45532e6ace37)

### Step 4:  Pushing a Docker image to Docker Hub:
First, we Sign In in Docker Hub and we create a repository. Second, we Tag the Docker Images before the Pushing by running this command in the root of the local repository:
```bash
docker tag <local_image>:latest <dockerhub_username>/<repository>:tagname
```
> Here we have 5 images: 
> ![image](https://github.com/hhanae/docker-demo-lab/assets/97336261/9e114081-0c06-41d5-9a17-2766990eda10)

Then, we push the images, by running this command:
```bash
docker push <dockerhub_username>/<repository>:tag
```

> [@hanim_hanae]([https://twitter.com/amit_merchant](https://hanim-hanae.vercel.app/)https://hanim-hanae.vercel.app/)

