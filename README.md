# Article-on- Calgary-Central-library
Enhancing-Community-Access-Database-Solutions
│
├── README.md
├── database_design
│   ├── Database_Design_Overview.md
│   ├── Core_Database_Components.md
│   └── ERD_Diagram.png
├── sql_scripts
│   ├── create_tables.sql
│   ├── insert_data.sql
│   └── queries.sql
├── reports
│   └── Data_Reporting_Analytics.md
└── LICENSE

# Enhancing Community Access: Database Solutions for the Central Library of Calgary

This repository contains the design and implementation of a database system for the Central Library of Calgary. The database aims to automate core library operations, such as catalog management, user registration, and event scheduling, while supporting the library's future growth and integration of new services.

## Table of Contents
- [Mission Statement](#mission-statement)
- [Objectives](#objectives)
- [Core Database Design Components](#core-database-design-components)
- [Key Benefits](#key-benefits)
- [SQL Scripts](#sql-scripts)
- [Reports](#reports)
- [License](#license)

## Mission Statement
The mission of this project is to design a robust and scalable database system for the Central Library of Calgary that:

1. Enhances access to physical and digital resources.
2. Automates library operations for efficiency.
3. Provides an intuitive experience for both staff and library members.
4. Supports scalability for future growth and services integration.

## Objectives
- **Resource Management**: Real-time tracking of the library’s stock of physical and digital resources.
- **User Registration and Management**: Simplified user account creation and management, with tracking of borrowed items, due dates, and event participation.
- **Data Reporting and Analytics**: Generation of detailed reports on borrowing patterns, event attendance, and library usage for informed decision-making.

## Core Database Design Components
The system revolves around several well-structured tables for smooth data flow between different library functions. More details can be found in the `database_design` folder.

1. **Branch Table**: Stores branch-specific information.
2. **Employee Table**: Tracks employee roles and assignments.
3. **Books Table**: Catalogs both physical and digital resources.
4. **Customer Table**: Manages user information.
5. **Issue Status Table**: Manages the borrowing process.
6. **Return Status Table**: Tracks item returns and fines.
7. **Event and Program Data Table**: Organizes library events and programs.
8. **Supplier Table**: Tracks supplier details for resource acquisition.

## Key Benefits
1. **Operational Efficiency**: Automation of key operations such as catalog management, user registration, and event scheduling.
2. **User-Friendly Experience**: Users can easily track available resources and register for events online.
3. **Accurate Resource Management**: Real-time tracking of resource availability across branches.
4. **Data-Driven Decision Making**: The system generates reports to guide future investments and initiatives.
5. **Scalability and Future-Proofing**: The database is scalable and can integrate future technologies, such as RFID and e-book lending.

For more details on these components, check the `database_design/Core_Database_Components.md`.

## SQL Scripts
The SQL scripts for creating, populating, and querying the database are available in the `sql_scripts` folder.
- `create_tables.sql`: SQL commands for creating the database tables.
- `insert_data.sql`: Sample data for populating the tables.
- `queries.sql`: Queries to manage library operations.

# Database Design Overview

The database system for the Central Library of Calgary is designed to manage the library’s core functions such as resource management, user registration, event scheduling, and data reporting. The design ensures smooth data flow between different functions and guarantees scalability.

## Key Components:
- **Branches**: Manages the different library branches and their resources.
- **Employees**: Tracks employee roles and assignments.
- **Books**: Catalogs all available resources, both physical and digital.
- **Customers**: Manages library user accounts and borrowing history.
- **Issue and Return Status**: Handles book lending and return processes.
- **Events and Programs**: Manages event scheduling and participation.
- **Suppliers**: Tracks supplier details for resource acquisition.

  # Core Database Design Components

## 1. Branch Table
- **Purpose**: Stores branch-specific information.
- **Fields**: `Branch_ID`, `Branch_Name`, `Address`, `Contact`

## 2. Employee Table
- **Purpose**: Tracks employee roles and branch assignments.
- **Fields**: `Employee_ID`, `Name`, `Position`, `Salary`, `Branch_ID`, `Hired_Date`

## 3. Books Table
- **Purpose**: Catalogs all physical and digital resources.
- **Fields**: `Book_ID`, `Title`, `Author`, `ISBN`, `Publish_Date`, `Branch_ID`

## 4. Customer Table
- **Purpose**: Manages user data.
- **Fields**: `Customer_ID`, `Name`, `Email`, `Phone`

## 5. Issue Status Table
- **Purpose**: Manages borrowing process.
- **Fields**: `Issue_ID`, `Book_ID`, `Customer_ID`, `Issue_Date`, `Due_Date`, `Status`

## 6. Return Status Table
- **Purpose**: Tracks the return of borrowed items.
- **Fields**: `Return_ID`, `Issue_ID`, `Return_Date`, `Fine`

## 7. Event and Program Data Table
- **Purpose**: Organizes library events and programs.
- **Fields**: `Event_ID`, `Event_Name`, `Branch_ID`, `Date`, `Description`

## 8. Supplier Table
- **Purpose**: Tracks suppliers for resource acquisition.
- **Fields**: `Supplier_ID`, `Name`, `Email`, `Phone`

CREATE TABLE Branch (
    Branch_ID INT PRIMARY KEY,
    Branch_Name VARCHAR(255),
    Address VARCHAR(255),
    Contact VARCHAR(50)
);

CREATE TABLE Employee (
    Employee_ID INT PRIMARY KEY,
    Name VARCHAR(255),
    Position VARCHAR(100),
    Salary DECIMAL(10, 2),
    Branch_ID INT,
    Hired_Date DATE,
    FOREIGN KEY (Branch_ID) REFERENCES Branch(Branch_ID)
);

INSERT INTO Branch (Branch_ID, Branch_Name, Address, Contact)
VALUES (1, 'Central Library', '123 Library St', '123-456-7890');

INSERT INTO Employee (Employee_ID, Name, Position, Salary, Branch_ID, Hired_Date)
VALUES (1, 'Jane Doe', 'Librarian', 45000, 1, '2023-06-15');

-- Get all available books
SELECT * FROM Books WHERE availability = TRUE;

-- List all upcoming events
SELECT * FROM Events WHERE Date >= CURDATE();

# Data Reporting and Analytics

The database system generates various reports that allow the library to track its operations, including:

- **Borrowing Patterns**: Data on the most borrowed books and peak borrowing times.
- **Event Attendance**: Reports on which events are most popular.
- **Library Usage**: Insights into user demographics and library usage trends.

These reports provide data-driven insights for better decision-making by library management.



 
 
