## What is Spring Boot

Spring Boot helps to quickly create Spring-based applications without having to write the same boilerplate
configuration over again.

Spring is a popular JavaEE framework for building web and enterprise applications.

Why is it popular
* Dependency injection
* Powerful database transaction management capabilities
* Can be integrated with other Java frameworks like JPA/Hibernate, Struts/JSF, etc.
* Web MVC (Model View Controller) framework for building web applications

Problems with Spring and how Spring Boot helps:
* Spring-based apps have lots of configurations: Component scan, Dispatcher Servlet, View resolver, Web jars, etc.
* If using Hibernate and JPA in the same Spring MVC app, you need to configure a Data source, Entity manager factory/session/factory, Transaction manager, etc.
* When you use cache, message queue, NoSQL in the same app, you need to configure Cache configuration, Messsage queue configuration, NoSQL database configuration.
* The need to maintain all integration of different Jar dependencies and compatible versions.

How Spring Boot helps:
* Spring Boot has auto configuration
    * Spring Boot will automatically configure the application based on the added jar dependencies
* Spring Boot provides embedded Tomcat server
    * Create a jar file and deploy it in an embdedded Tomcat server
* Spring Boot provides starter modules
    * They are pre-configured with the most commonly used library dependencies
    * It will also configure the commonly registered beans such as DispatcherServlet.
    * It sucks to have to search for compatible library versions and configure them manually.
* Spring Boot actuator
    * Production ready features such as rest endpoints.
* Externalized Configuations
    * No need to externalize the configuration based on the environment (Develepment, testing, etc.)


Talk about Spring Boot starter parent dependency

Talk about annotation @springbootapplication
* it has 3 other annotations automatically
    * @EnableAutoConfiguration
    * @ComponentScan
    * @Configuration
Because of that, you can define the beans within the main entry point of the program (Application class) without using a config file. 
We don't have to manually create the application context
