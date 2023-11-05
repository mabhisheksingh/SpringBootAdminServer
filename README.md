# SpringBootAdminServer

## Without any client server
![Admin Server with any client GUI](/Images/with&20a%20admin%20client%20server.png)

## With one client-server
![Admin Server with any client GUI](/Images/with%20a%20admin%20client%20server.png)

This is a Spring boot admin server to monitor and see other application **[discovery client or Admin client]** actuator data in GUI

## Config needs to change in Admin Server
```yaml
server:
  port: 9000

spring:
  application:
    name: spring-admin-server
```

## keynote while using admin client  in application
```text
If you already using Spring Cloud Discovery for your applications you don’t have to add the Spring Boot Admin Client to your applications. 
Just make the Spring Boot Admin Server a DiscoveryClient, the rest is done by our AutoConfiguration.

The following steps are for using Eureka, but other Spring Cloud Discovery implementations are supported as well. 
There are examples using Consul and Zookeeper.

Also, have a look at the Spring Cloud documentation.
```

## Config needs to change in Admin client side
#### Define port and server in the client  
```yaml
server:
  port: 8081
  address: 127.0.0.1

```
#### Define the admin server URL and out instance name on the client side.
```yaml
spring:
  boot:
    admin:
      client:
        auto-registration: true
        enabled: true
        url: http://localhost:9000
        instance:
          name: my-client-1
  application:
    name: WebFluxSpringApplication

```

