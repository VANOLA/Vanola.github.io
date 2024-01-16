### JDBC vs JPA vs Hibernate ###
In this post, we'll discuss the differences between JDBC, JPA, and Hibernate. When I was building my first CRUD app, these were just some of the acronyms I heard. As a beginner, it was a little overwhelming. But as we'll see in this post, it is not difficult to understand at all. 

### What is JDBC ###
JDBC stands for Java Database Connectivity. It also is an API that connects data to databases. JDBC is a connection of classes and interfaces. JDBC writes queries written in SQL. JDBC can connect to any database management system if it has a driver. One con of 
JDBC is that it requires a lot of code as you have to include details such as table names and column names. 

#### What is JPA ####
JPA stands for Jakarta (Java) Persistence API. It is a collection of classes and methods that facilitate the persistent storage of data into a database. Internally, it uses JDBC to facilitate and standardize object-relational mapping (ORM). It manage relational data in Java apps by defining the data internally instead of relying on vendor-specific mapping implementations. This is done by using annotations or XML to map objects to tables in a database. JPA, however, is only a specification and does not provide an implementtion.

#### What is Hibernate ####
Hiberate provides a JPA implementation to map database records to objects. It is an 
open-source and lightweight tool. It generates the SQL statements needed for database
operations. 

### What is Spring Data JPA ###
Spring provides the Spring Data JPA library to reduce the amount of boilerplate code required to implement the Data Access Object (DAO) layer. It is an abstraction layer that "hides" JPA.


<a href="https://www.geeksforgeeks.org/difference-between-jdbc-and-hibernate-in-java/" target="blank">JDBC vs Hibernate</a>
<a href="https://www.ibm.com/docs/en/informix-servers/12.10?topic=started-what-is-jdbc">JDBC</a>
<a href="https://www.ibm.com/docs/en/was-liberty/nd?topic=liberty-java-persistence-api-jpa">What is JPA</a>
<a href="https://hackernoon.com/the-difference-between-jdbc-jpa-hibernate-and-spring-data-jpa">JDBC, JPA, Hibernate</a>