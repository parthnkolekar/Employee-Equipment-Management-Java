# Project Report: Employee & Equipment Management System

## Student Details
- Student name: [Enter name]
- USN: [Enter USN]
- Department/section: [Enter details]
- Subject: [Enter subject]
- Date: [Enter date]

## 1. Introduction
This Java desktop application manages employee records, equipment inventory and equipment assignments using a graphical interface.

## 2. Problem Statement
Manual records can result in duplicate entries, missing information and difficulty tracking equipment assignments. This application centralizes those tasks.

## 3. Objectives
- Maintain employee and equipment records.
- Implement Create, Read, Update and Delete (CRUD).
- Assign or unassign equipment.
- Validate user input and display helpful messages.
- Store records persistently in a relational database.

## 4. Technologies
Java 21, Java Swing, FlatLaf, JDBC, H2 Database, SQL, Maven, IntelliJ IDEA.

## 5. Architecture
User → Swing GUI → JDBC → H2 database.

## 6. Modules
Dashboard; Employee Management; Equipment Management; Equipment Assignment.

## 7. Database Design
Employees: id (primary key), name, email (unique), department.
Equipment: id (primary key), name, category, status, employee_id (foreign key to employees.id).

## 8. Testing
Record actual results after running the application.

| Test | Expected result | Actual result |
|---|---|---|
| Add employee | Employee appears in table | [Fill in] |
| Empty employee fields | Validation message appears | [Fill in] |
| Update employee | Selected record updates | [Fill in] |
| Delete employee | Record removed after confirmation | [Fill in] |
| Add equipment | Equipment appears in table | [Fill in] |
| Assign equipment | Assigned status and employee shown | [Fill in] |
| Unassign equipment | Status becomes Available | [Fill in] |
| Restart app | Saved records remain | [Fill in] |

## 9. Screenshots
Insert screenshots of dashboard, Employees tab, employee added, validation message, Equipment tab, equipment added, assignment, and persistence after restart.

## 10. Conclusion
The application demonstrates a Java GUI connected to H2 and supports CRUD operations, equipment assignment and persistent local storage.
