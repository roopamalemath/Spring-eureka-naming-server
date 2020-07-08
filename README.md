# spring-eureka-naming-server

Eureka Naming server has two features
1. Service Registry
2. Service Discovery

1. Service Registry - Every Microservice have to register wih eureka Naming server

steps to be followed to register with Eureka Naming server
1. Add a dependency in pom.xml

    <dependency>
	<groupId>org.springframework.cloud</groupId>
	<artifactId>spring-cloud-starter-netflix-eureka-server</artifactId>
   </dependency>
    
2. To enable eureka naming server

you need a special annotation in main class i.e,
@EnableEurekaServer

3. application.properties
configure naming and other stuff

spring.application.name=netflix-eureka-naming-server
server.port=8761
eureka.client.fetch-registry=false
eureka.client.register-with-eureka=false

eureka.client.register-with-eureka=false - dont want to register itself with naming server

eureka.client.register-with-eureka=false - disable the fetch registry

2. Service Discovery - when they want a details of another microservice they should do a service discovery

steps to be followed for service discovery

1. add a dependency

    <dependency>
	<groupId>org.springframework.cloud</groupId>
	<artifactId>spring-cloud-starter-netflix-eureka-client</artifactId>
    </dependency>
    
2. To register with the naming server 

add a special annoatation in main class
@EnableDiscoveryClient - to enable the discovery client

3. Configure the url for eureka naming server

eureka.client.service-url.default-zone=http://localhost:8761/eureka

eureka server is running on port 8761  

