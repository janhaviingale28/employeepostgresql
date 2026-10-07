# Spring Boot + PostgreSQL Connection

This project is a beginner-friendly example for connecting a Spring Boot application to PostgreSQL using Spring Data JPA and Hibernate.

## 1. Before running

Make sure PostgreSQL is installed and pgAdmin shows a database named:

employee_db

Default connection details:

- Host: localhost
- Port: 5432
- Database: employee_db
- Username: postgres
- Password: your PostgreSQL password

## 2. Configure application.properties

Open:

src/main/resources/application.properties

Find:

spring.datasource.password=CHANGE_ME

Replace CHANGE_ME with the password you created for PostgreSQL.

Example:

spring.datasource.password=MyPassword123

Do NOT commit your real password to GitHub.

## 3. Important properties

spring.datasource.url=jdbc:postgresql://localhost:5432/employee_db
spring.datasource.username=postgres
spring.datasource.password=YOUR_PASSWORD
spring.jpa.hibernate.ddl-auto=update
spring.jpa.database-platform=org.hibernate.dialect.PostgreSQLDialect

## 4. Import into Eclipse

1. Extract the ZIP.
2. Open Eclipse.
3. File -> Import.
4. Maven -> Existing Maven Projects.
5. Select the extracted project folder.
6. Click Finish.
7. Wait for Maven dependencies to download.

## 5. Run

Open EmployeePostgresqlApplication.java.

Right-click:
Run As -> Spring Boot App

If the database connection is correct, the application should start on port 8080.

## 6. Test

Open:

http://localhost:8080/api/health

Expected response:

Spring Boot application is running and PostgreSQL configuration is loaded.

The Employee entity is included so Hibernate can create/update the employees table when the application starts.

## 7. If you get a password error

Check:

- PostgreSQL service is running.
- Database employee_db exists.
- Username is postgres.
- Port is 5432.
- The password in application.properties exactly matches the PostgreSQL password.

Typical error:
FATAL: password authentication failed for user "postgres"

Fix the password value and restart the Spring Boot application.
