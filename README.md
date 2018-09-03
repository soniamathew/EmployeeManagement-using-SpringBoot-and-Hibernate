EMPLOYEE MANAGEMENT RESTFUL WEB SERVICE USING SPRINGBOOT AND HIBERNATE :

********************** COMPILING AND EXECUTING ******************************
-----------------------------------------------------------------------------

**** In IntelliJ IDEA :

     Build the project using : ./gradlew build
     Run the Employee Application.
     Then the SpringBoot Application class will be run, tomcat will get started on port 9000 and mysql connection is also made.



**** In MySQL.prefpane :

     Start the mysql server in MySQL server 



**** In the MySQLWokrkbench :

    * First create a database named employeez using the query :
    CREATE SCHEMA `employeez` ;
                                                                         
    * Then create the table employeez in the database employeez using the query :

    CREATE TABLE `employeez`.`employeez` (
    `id` INT GENERATED ALWAYS AS (),
    `name` VARCHAR(45) NOT NULL,
    `salary` VARCHAR(45) NOT NULL,
     PRIMARY KEY (`id`));



**** In Postman :

     Make the Rest API requests as follows :-
     
   * CRUD OPERATIONS :   (CREATE, READ BY ID, UPDATE AND DELETE BY ID)
     
     create : 
             method : POST , API endpoint : http://localhost:9000/employee/api/create
     
     read : 
           method : GET , API endpoint : http://localhost:9000/employee/api/read/{id}              -give the id.
     
     update : 
           method : PUT , API endpoint : http://localhost:9000/employee/api/update
     
     delete : 
           method : DELETE , API endpoint : http://localhost:9000/employee/api/delete/{id}         -give the id.
     
     
     After hitting the Rest APIs and the MySQL database, the results wil be displayed in postman as well as console of the IntelliJ IDEA.


******************************** PROGRAM LOGIC ******************************
-----------------------------------------------------------------------------


Spring Boot makes it easy to create stand-alone, production-grade Spring based Applications that can run.

Hibernate understands the mappings that we add between objects and tables and it ensures that data is stored/retrieved from the database based on the mappings.
Hibernate also provides additional features on top of JPA.

Here in this project we are having the following :

The POJO class : Employee ,inside the package : com.employee.employee.sample.entity .
The Controller class : EmployeeManagementController, inside the package : com.employee.employee.controller .
The Service Implemenation class : EmployeeManagementService, inside the package : com.employee.employee.service .
The Service Interface : IEmployeeManagementService, inside the package : com.employee.employee.service .
The main class or the Application classs : EmployeeApplication, inside the package : com.employee.employee .
The DAO Interface : EmployeeDaoInterface, inside the package : com.employee.employee.sample.dao . (it extends the CRUD repository)
There is also an AppConfig class inside the package : com.employee.employee.sample.config , but this is used only if we are using datasource,since we are using Hibernate it was commented.

When we run the Application, the tomcat will get started at port 9000, then start the MySQL server and connect the local host in the MySQL Workbench,
after hitting the rest api in postman, the control will go to the EmployeeManagementController and from there control goes to EmployeeManagementService and EmployeeDaoInterface and then it responds with various status after performing the operations.

