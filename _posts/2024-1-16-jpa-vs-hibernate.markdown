---
layout: post
title:  "JDBC vs JPA vs Hibernate"
author: Vanessa Arreola
date:   2024-01-16 06:00:00 -0600
categories: spring hibernate
tags: spring hibernate
comments: true
---

### JDBC vs JPA vs Hibernate ###
In this post, we'll discuss the differences between JDBC, JPA, and Hibernate. When I was building my first CRUD app, these were just some of the acronyms I heard. As a beginner, it was a little overwhelming. But as we'll see in this post, it is not difficult to understand. 

### What is JDBC ###
JDBC stands for Java Database Connectivity. It is an API that connects data to databases. JDBC is a collection of classes and interfaces. JDBC writes queries written in SQL, and can connect to any database management system if it has a driver. One con of JDBC is that it requires a lot of code as you have to include details such as table names and column names and write the queries. 

#### What is JPA ####
JPA stands for Jakarta (Java) Persistence API. It is a collection of classes and methods that facilitate the persistent storage of data into a database. Internally, JPA uses JDBC to facilitate and standardize object-relational mapping (ORM). It manages relational data in Java apps by defining the data internally instead of relying on vendor-specific mapping implementations. This is done by using annotations or XML to map objects to tables in a database. JPA, however, is only a specification and does not provide an implementtion.

#### What is Hibernate ####
Hiberate provides a JPA implementation to map database records to objects. It is an 
open-source and lightweight tool, and is arguably the most popular ORM framework. It generates the SQL statements needed for database operations.

#### What is Spring Data JPA ####
Spring provides the Spring Data JPA library to reduce the amount of boilerplate code required to implement the Data Access Object (DAO) layer. It is an abstraction layer that "hides" JPA. When you use Spring Data JPA with Spring Boot, all you need to do is provide the host for the database, the username, and the password. 

#### Helpful Resources ###
<a href="https://www.geeksforgeeks.org/difference-between-jdbc-and-hibernate-in-java/" target="blank">JDBC vs Hibernate</a>

<a href="https://www.ibm.com/docs/en/informix-servers/12.10?topic=started-what-is-jdbc">JDBC</a>

<a href="https://www.ibm.com/docs/en/was-liberty/nd?topic=liberty-java-persistence-api-jpa">What is JPA</a>

<a href="https://hackernoon.com/the-difference-between-jdbc-jpa-hibernate-and-spring-data-jpa">JDBC, JPA, Hibernate</a>