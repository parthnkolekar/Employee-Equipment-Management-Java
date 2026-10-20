# Employee & Equipment Management System

1. Project Overview

The Employee & Equipment Management System is a Java-based desktop application developed to manage employee information, company equipment, and equipment assignments.

The application provides a graphical user interface (GUI) that allows users to add, view, update, and delete employee and equipment records. It also supports assigning equipment to employees and managing those assignments.

The project uses Java Swing for the user interface and an H2 database for storing data persistently. The interface is styled using FlatLaf to provide a modern and user-friendly appearance.

Project Objectives

Maintain employee records in one place.

Maintain equipment details and availability.

Assign equipment to employees.

Prevent invalid assignments, such as assigning unavailable equipment.

Store information persistently in a database.

Provide a simple graphical interface for performing management operations.

2. Technologies Used

Technology

Purpose

Java 21

Core programming language

Java Swing

Desktop graphical user interface

FlatLaf

Modern styling for Swing components

JDBC

Communication between Java and the database

H2 Database

Persistent data storage

Maven

Dependency management and project building

JUnit 5

Unit testing, if test classes are included

IntelliJ IDEA / VS Code

Development environment

3. System Requirements and Prerequisites

Before running the project, ensure that the following software is installed:

Java Development Kit (JDK) 21 or a compatible supported version.

Apache Maven, if the project is run using Maven commands.

A code editor or IDE, such as IntelliJ IDEA or Visual Studio Code.

Windows, Linux, or another operating system that supports Java Swing.

An internet connection may be required the first time Maven downloads project dependencies.

Verify the installation

Open a terminal or PowerShell window and run:

java -version

Check Maven using:

mvn -version

If the mvn command is not recognized, install Maven or configure its bin directory in the system PATH. If a working run.bat file is provided, it may offer an alternative way to start the application.

4. Project Structure

The project follows a Maven-based Java project structure.

Employee-Equipment-Management-Java/
│
├── src/
│   ├── main/
│   │   └── java/
│   │       └── com/lab/management/
│   │           └── ManagementApp.java
│   │
│   └── test/
│       └── java/         
├── data/                 
├── pom.xml
├── README.md
└── run.bat                

The exact package structure may contain additional Java classes for database access, employee management, equipment management, and assignment operations.

5. Installation and Setup

Follow these steps to install and run the application.

Step 1: Obtain the project

Download or extract the project ZIP file, or clone the repository if it is hosted on GitHub.

Step 2: Open the project

Open the extracted project folder in IntelliJ IDEA, Visual Studio Code, or another Java-compatible IDE.

Make sure you open the folder containing pom.xml.

Step 3: Resolve dependencies

Open the terminal in the project directory and run:

mvn clean compile

Maven will clean previous build files, resolve required dependencies, and compile the source code.

Step 4: Start the application

Run the following command from the project root directory:

mvn clean compile exec:java

This command compiles the application and starts its configured main class.

If the project includes a working run.bat file, you can also use that file to start the application on Windows.

Step 5: Use the application

After the application launches, use the available employee and equipment screens to manage records and assignments.

6. Running the Frontend and Backend

This project is a standalone Java Swing desktop application, not a separate React frontend and Spring Boot backend application.

Frontend

The frontend is implemented using Java Swing. It displays the management screens, input fields, buttons, tables, and other interface components.

The GUI is launched as part of the main Java application:

mvn clean compile exec:java

Backend and data operations

The application's business logic and database operations run within the same Java application. JDBC is used to communicate with the H2 database.

There is no separate backend server to start in the current architecture.

API and base URL configuration

The current application does not require an HTTP API or API base URL because it communicates directly with the database through JDBC.

If the project is later converted to a REST-based architecture, an API base URL can be documented here. For the current desktop application, this setting is not applicable.

7. Database Configuration

The application uses the H2 database to store employee, equipment, and assignment information.

The database connection is configured in the Java source code. The current configuration uses a file-based database:

private static final String URL = "jdbc:h2:file:./data/labdb";

The connection method uses the configured JDBC URL and local database credentials.

Database features

Stores records beyond the current application session.

Allows the application to retrieve previously saved data.

Uses JDBC for database communication.

Supports database tables for the application's management operations.

The database file is normally created in the project's data directory when the application initializes the database. The actual file may have an .mv.db extension.

Important: Run the application from the project root directory when using the relative database path. Keep the database file if you want to retain saved records. Do not delete it while trying to reset or troubleshoot the application unless you intentionally want to remove the stored data.

No separate database server installation is normally required for an embedded H2 database.

8. Main Features

Employee Management

Add new employee records.

View employee details.

Update existing employee information.

Delete employee records when permitted by the application logic.

Equipment Management

Add equipment records.

View equipment details.

Update equipment information.

Delete equipment records when permitted by the application logic.

Equipment Assignment

Assign available equipment to an employee.

Track the employee associated with assigned equipment.

Prevent invalid operations through application-level validation.

Unassign equipment when the corresponding functionality is available.

User Interface

Graphical desktop interface built with Java Swing.

Modern component styling using FlatLaf.

Tables for displaying employee and equipment records.

Input controls and action buttons for management operations.

A dashboard-style layout for easier navigation, where implemented.

9. Testing Instructions

Test the application using sample data that does not contain real personal or confidential information.

Suggested manual tests

Add a sample employee and verify that the record appears in the employee table.

Update the employee's details and confirm that the changes are displayed.

Add a sample equipment item and verify that it appears in the equipment table.

Update the equipment details.

Assign available equipment to an existing employee.

Verify that invalid employee or equipment IDs are handled appropriately.

Try assigning equipment that is already assigned and check that the application prevents the invalid operation, if this validation is implemented.

Close and reopen the application to verify that saved records remain available.

Test deletion and unassignment operations, if implemented.

Automated tests

If the project includes JUnit 5 test classes, execute:

mvn test

This command runs the automated tests configured in the Maven project. If no automated tests are included, use the manual test cases above and do not claim that automated tests have passed.

10. Test Accounts and Credentials

The application does not require separate web frontend or backend login credentials unless an authentication screen has been added to the project.

Do not include personal account passwords, production credentials, API keys, access tokens, or other secrets in this README or in the source repository.

The local H2 connection configuration is an application database setting, not a user login account. Any credentials used in a shared or deployed environment should be configured securely and approved for sharing.

11. Known Limitations

The application is designed as a desktop application rather than a web application.

There is no separate REST API or remotely hosted backend in the current architecture.

The embedded database is suitable for a local project but may require a different database architecture for multi-user deployment.

Database file paths depend on the application's working directory when relative paths are used.

The application requires a compatible Java runtime.

Features such as user authentication, role-based permissions, audit logging, and remote access are not included unless explicitly implemented.

Automated test coverage depends on the test classes available in the project.

The appearance and supported operations depend on the components and validation logic implemented in the source code.

12. Troubleshooting

Maven command is not recognized

Install Apache Maven and configure its bin directory in the Windows PATH. Restart the terminal and verify using mvn -version.

Dependencies fail to download

Check your internet connection, Maven configuration, and the dependency declarations in pom.xml.

Application does not launch

Verify the Java version, compile errors, Maven configuration, and main-class configuration.

Database records are missing

Check that the application is using the expected working directory and database file. A different working directory can cause a relative path to point to a different database.

Database connection errors

Verify the JDBC URL and connection configuration in the source code. Avoid deleting an existing database file as a troubleshooting step unless its contents are no longer required.

13. Future Enhancements

Potential improvements include:

User authentication and role-based access control.

Search, filtering, and sorting.

Reports for employee and equipment assignments.

Exporting records to CSV or PDF.

Improved validation and error messages.

Additional automated tests.

Backup and restore functionality.

A REST API and web interface if the application is extended into a client-server system.

14. Conclusion

The Employee & Equipment Management System demonstrates the use of Java programming, desktop GUI development, database connectivity, and CRUD operations in a practical management application. It provides a foundation for managing employee information, equipment records, and assignments, with opportunities for future improvements.

## 12. Author

Student Name: Parth Nikhil Kolekar

Project: Employee & Equipment Management System

Course/Section: Web Design and Development / 3rd sec E

