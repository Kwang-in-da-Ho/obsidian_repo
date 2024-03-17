# Layers & Testing Method
## Layers of a Spring Boot Application
![[Pasted image 20240318010559.png]]
* Controller : `@SpringBootTest` (Spring context managed bean)
	* Tests on response data and HTTP-related functions
* Service, Repository : `@SpringBootTest` (Spring context managed bean)
	* Tests on data
* Domain : plain test (POJO)
### What is `@SpringBootTest` ?
The `@SpringBootTest` annotation is used in Spring Boot applications for integration testing. Its exact role is to configure and bootstrap the Spring `ApplicationContext` for integration tests, providing a way to test the entire application context. Here's a breakdown of its role:

1. **Application Context Setup**:
    
    - When you annotate a test class with `@SpringBootTest`, it instructs Spring Boot to load the entire application context.
    - This means that all the beans, configurations, and components defined in your Spring Boot application will be instantiated and configured for testing.
2. **Realistic Environment**:
    
    - `@SpringBootTest` tries to mimic the actual runtime environment of your application as closely as possible.
    - It loads properties from application.properties or application.yml files, so you can test your application with realistic configurations.
3. **Bean Injection**:
    
    - It allows you to autowire beans into your test classes, just like you do in your regular Spring Boot application.
    - This enables you to test interactions between different components of your application within the context of integration tests.
4. **Web Environment Configuration**:
    
    - By default, `@SpringBootTest` starts the embedded web server, enabling you to perform HTTP requests against your application and test its RESTful endpoints.
    - You can configure the web environment using the `webEnvironment` attribute of `@SpringBootTest`. For example, you can specify `webEnvironment = SpringBootTest.WebEnvironment.RANDOM_PORT` to start the server on a random port.
5. **Classpath Scanning**:
    
    - `@SpringBootTest` scans your application's classpath to find relevant components to load into the application context.
    - It uses the same component scanning mechanism as your regular Spring Boot application, allowing you to easily test your controllers, services, repositories, etc.
6. **Testing with Embedded Databases**:
    
    - If your application uses an embedded database like H2, `@SpringBootTest` can automatically configure and set up the database for testing purposes.
7. **Transaction Management**:
    
    - `@SpringBootTest` provides transaction management support for integration tests, allowing you to roll back transactions after each test method to maintain a consistent state of the database.

In summary, `@SpringBootTest` is a powerful annotation in Spring Boot testing that facilitates integration testing by setting up the entire application context, configuring the environment, and enabling interaction with various components of your application.
### Which Layer should be tested?
* **service layer**
* 