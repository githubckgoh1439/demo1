
Build Restful CRUD API for a Student Registration Application using Spring Boot, Mysql, JPA and Hibernate.

--------------------------------------------
1. Requirements
--------------------------------------------
- Java : version 1.8.x
- Maven : version 3.x.x
- Mysql : version 5.6.x


--------------------------------------------
2. Steps to Setup
--------------------------------------------

1. Clone the application using git client

 - git clone https://github.com/githubckgoh1439/demo1 git_demo1

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

--- GET /school/students/

--- POST /school/students/

--- GET /school/students/{studentId}

--- PUT /school/students/{studentId}

--- DELETE /school/students/{studentId}

You can test them using postman or any other rest client.


----------------------------------------------------------------------------------------
4. Learn more : Dockerizing a Spring Boot service which leverages a mysql storage
----------------------------------------------------------------------------------------

Step-1.  
Download this mysql.zip from github then unzip and upload into docker-host-path where : 

- /home/demo1/

	
Step-2. 

Create a [bridge-network] under docker environment using this CLI :
  
   - docker network create -d bridge gp-bridgenet-01

   - As example result like this : 

     root@node03:~# docker network ls

    NETWORK ID          NAME                DRIVER              SCOPE

    f7b898a15847        gp-bridgenet-01     bridge              local


Step-3. 

Download from Dockerhub using below CLI :  

- docker pull dockerckgoh1439/mysql-demo1:latest
- docker pull dockerckgoh1439/demo01:0.0.2

- As example result like this : 

  root@node03:~# docker images

  REPOSITORY                          TAG                  IMAGE ID            CREATED             SIZE

  dockerckgoh1439/demo01              0.0.2                a737a6ff5ee4        6 hours ago         131MB

  dockerckgoh1439/mysql-demo1         latest               f850a6fb2a51        6 hours ago         226MB


Step-4. 

Download this docker-compose.yml from github and upload into docker-host-path where /home/demo1/ then run below CLI :

 - docker-compose up -d


 - As example result like this : 

   root@node03:~# docker ps

   CONTAINER ID        IMAGE                                                  COMMAND                  CREATED             
   STATUS                    PORTS                    NAMES

   98390d086353        dockerckgoh1439/demo01:0.0.2                           "java -jar app.jar"      42 
   seconds ago      Up 40 seconds             0.0.0.0:8181->8181/tcp   student_dockerhub01

   c9d29d5c87fc        dockerckgoh1439/mysql-demo1:latest                     "/entrypoint.sh my..."   43 
   seconds ago      Up 41 seconds (healthy)   0.0.0.0:3306->3306/tcp   mysql_dockerhub01



Step-5. 

Open new browser and go to :

- http://localhost:8181/school/students/



----------------------------
5. Demo Purpose - using postman
----------------------------

1. Method [POST] : ADD 

   - http://cubemulus.com:8181/school/students/

   - {"studentCode" : "id_1", "name": "name1", "ic": "ic_no_1", "age": "11", "sex": "M", "phone": "0312345678", "address": "DESA JAYA", "year": "YEAR-1", "studentClass": "class_blue", "emergencyContact": "mother"}


2. Method [GET] : List all the students 

  - http://cubemulus.com:8181/school/students/


3. Method [GET] : List student whose id = 1

 - http://cubemulus.com:8181/school/students/1


4. Method [PUT] : UPDATE 

 - http://cubemulus.com:8181/school/students/1

  - {"studentCode" : "id_1", "name": "name1", "ic": "ic_1", "age": "11", "sex": "M", "phone": "0312349999", "address": "DESA JAYA", "year": "YEAR-1", "studentClass": "class_blue", "emergencyContact": "mum"}

