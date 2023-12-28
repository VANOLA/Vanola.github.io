### Constructor vs Setter vs field Based Dependency Injection ###

**Use @Autowired annotation**

* 1 uses setter the other constructor the other field
* Spring will find the @Autowired annotation and call the setter to inject the depenedency
* Spring will find the @Autowired annotation and call the constructor to inject the dependency

**When to use**
* Construcor
    * For mandatory dependencies so that your bean is ready to use when it is called for the first time
* Setter
    * For optional dependencies
    * To avoid circular dependencies
    * Why should we avoid circular dependencies?
* Field
    * dependency is injected directly in the filed
    * Annotate the class member with the @Autowired annotation
    * Uses reflection to inject the dependencies. Costlier.

**Field Drawbacks**
* Tight coupling with IOC container because it cannot be instantiated without it. Makes testing more like integration tests.
* Can't make final (immutable)
* Cannot be instantiated without reflection. 


***Single Responsibility Principle***
Class or component should be responsible for only one thing

Why is constructor based DI preferred?
* Available at initialization
* Immutability ***Because you can make final*** and avoid Null pointer exception, because they are initialized in constructor
* You don't have to create a setter for each dependency, just 1 constructor so less lines of code
* Preventing errors in test cases. Simplifies unit testing. Test cases executed only when dependencies are available. (You can forget to call setter).


You can use ```@Autowired``` to automatically inject a dependency (A class that uses another class or interface). Remember, Spring IOC creates and manages objects for us.
IOC stands for inversion of control. In dependency injection, the Spring container "injects" objects into other objects, or "dependencies". 

IOC containers allow for loose coupling of components.

* Use it when you have more than one constructor
* Optional if you only have 1 constructor

```@Qualifier``` is used when you have more than one Bean of the same type. What is a Bean? In Spring, the objects that form the backbone of your application and that are managed by the Spring IoC container are called beans. A bean is an object that is instantiated, assembled, and otherwise managed by a Spring IoC container.

```@Component``` ***Research this***

***Resources*** 
* <a href="https://www.baeldung.com/spring-dependency-injection" target="blank" >Dependency Injection</a> 
* <a href="https://www.baeldung.com/spring-bean" target="blank" >Beans</a> 