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

In this Lab Project, we created two micro-services: client-service & voiture-service. Furthermore, we created a service called Eureka Server which is a service registry that enables microservices to discover and communicate with each other. Finally, we created Spring Cloud Gateway Which is a powerful and flexible API gateway that provides capabilities such as routing, filtering, and load balancing. 

Here is a simplified representation of ou Project Structure:
```bash
microservices-demo
|-- Client
|   |-- src
|   |   |-- main
|   |       |-- java
|   |       |   |-- org.ensaj.clientservice
|   |       |       |-- ClientServiceApplication.java
|   |       |       |-- model
|   |       |       |   |-- Client.java
|   |       |       |-- repository
|   |       |       |   |-- ClientRepository.java
|   |       |       |-- service
|   |       |           |-- ClientService.java
|   |       |-- resources
|   |           |-- application.properties
|
|-- Voiture
|   |-- src
|   |   |-- main
|   |       |-- java
|   |       |   |-- org.ensaj.voitureservice
|   |       |       |-- VoitureServiceApplication.java
|   |       |       |-- model
|   |       |       |   |-- Voiture.java
|   |       |       |-- repository
|   |       |       |   |-- VoitureRepository.java
|   |       |       |-- service
|   |       |           |-- VoitureService.java
|   |       |       |-- resources
|   |       |           |-- application.properties
|
|-- eureka-server
|   |-- src
|   |   |-- main
|   |       |-- java
|   |       |   |-- org.ensaj.eurekaserver
|   |       |       |-- EurekaServerApplication.java
|   |       |       |-- resources
|   |       |           |-- application.properties
|
|-- gateway-service
|   |-- src
|   |   |-- main
|   |       |-- java
|   |       |   |-- org.ensaj.gateway
|   |       |       |-- GatewayServiceApplication.java
|   |       |       |-- config
|   |       |           |-- GatewayConfig.java
|   |       |       |-- resources
|   |       |           |-- application.properties

```


## Steps

provide you with a step-by-step guide on how to create separate Spring Boot projects for the client service, voiture service, Eureka server, and Spring Cloud Gateway.

### Step 1: Create a Spring Boot Project for Client MicroService
* Open your preferred IDE (such as IntelliJ IDEA).
* Create a new Spring Boot project, named client-service.
* Add the necessary dependencies, including Spring Web and Spring Data JPA.
* Create the Client entity.
* Create Client Repository.
* Implement the service.
* Implement the Controller.
* Configure the application.properties file for the Client:
* Modify the main class:
![image](https://github.com/hhanae/microservices_demo/assets/97336261/186881da-86c8-407f-8914-6dafb3d8f80c)


### Step 2: Create a Spring Boot Project for Voiture MicroService
* Open your preferred IDE (such as IntelliJ IDEA).
* Create a new Spring Boot project, named voiture-service
* Add the necessary dependencies, including Spring Web and Spring Data JPA.
* Create the Voiture entity.
* Create Voiture Repository.
* Implement the service.
* Implement the Controller.
* Configure the application.properties file for the Voiture.
* Modify the main class:
![image](https://github.com/hhanae/microservices_demo/assets/97336261/c52c445d-2c6d-409b-b87d-5155e13f58d7)

### Step 3: Create a Spring Boot Project for Eureka Server
* Open your IDE.
* Create a new Spring Boot project.
* Add the necessary dependencies, including Eureka Server.
* Annotate the main class with @EnableEurekaServer:
![image](https://github.com/hhanae/microservices_demo/assets/97336261/8839604f-403e-49e5-a7d2-495894a691d4)
* Configure the application.properties file for the Eureka server:
![image](https://github.com/hhanae/microservices_demo/assets/97336261/45da5504-c86f-465f-ad90-924e44e962d5)

### Step 4: Create a Spring Boot Project for Spring Cloud Gateway
* Open your IDE.
* Create a new Spring Boot project.
* Add the necessary dependencies, including Spring Cloud Gateway.
* Create a GatewayConfig class to configure routes:
![image](https://github.com/hhanae/microservices_demo/assets/97336261/994c4acd-08a4-434e-8326-cd0e7bf7c5b0)
* Configure the application.properties file for the gateway:
![image](https://github.com/hhanae/microservices_demo/assets/97336261/19f5a0b1-03e4-43cd-951b-49d0ba796d12)

We can get sure that the microservices are saved successfully by serving this url: http://localhost:8761

![image](https://github.com/hhanae/microservices_demo/assets/97336261/afbba49c-772b-4905-9ef1-4b394afb810e)


### Step 5: Run the Eureka Server, the Gateway, the Client Microservice & the Voiture Microservice
Browse for the microservice clients:
![image](https://github.com/hhanae/microservices_demo/assets/97336261/9a1206ac-475d-472f-83f2-4d2bc9460d14)
Browse for the microservice voitures:
![image](https://github.com/hhanae/microservices_demo/assets/97336261/a48c0937-2cde-4b92-bce2-1122937f637f)


### Step 6: Containerize the app:

If you want to persue the step of containerization please go to the <a href="https://cloud.google.com/learn/what-is-microservices-architecture?hl=fr#:~:text=L'architecture%20de%20microservices%20(ou,%C3%A9l%C3%A9ment%20ayant%20ses%20propres%20responsabilit%C3%A9s.)" target="_blank">docker-lab-demo</a> repository!


> [@hanim_hanae]([https://twitter.com/amit_merchant](https://hanim-hanae.vercel.app/)https://hanim-hanae.vercel.app/)

