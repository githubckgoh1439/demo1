


Build Restful CRUD API for a Student Registration Application 
using Spring Boot, Mysql, JPA and Hibernate.


--------------------------------------------
1. Requirements
--------------------------------------------
Java - version 1.8.x
Maven - version 3.x.x
Mysql - version 5.6.x


--------------------------------------------
2. Steps to Setup
--------------------------------------------
1. Clone the application
- git@github.com:callicoder/spring-boot-mysql-rest-api-tutorial.git

2. Create Mysql database
- create database [gp_school]

3. Change mysql username and password as per your installation
- open src/main/resources/application.properties
- change spring.datasource.username and spring.datasource.password as per your mysql installation


4. Build and run the app using maven
- Run this cmd script [mvnw package && java -jar target/goh-springboot-docker-1_0.jar]

The app will start running at http://localhost:8080/school/students/



--------------------------------------------
3. Explore Rest APIs
--------------------------------------------
The app defines following CRUD APIs.

http://192.168.38.33:8181/school/students/

GET /school/students/

POST /school/students/

GET /school/students/{studentId}

PUT /school/students/{studentId}

DELETE /school/students/{studentId}

You can test them using postman or any other rest client.



--------------------------------------------
4. Learn more
--------------------------------------------


Title :
Dockerizing a Spring Boot service which leverages a mysql storage.












