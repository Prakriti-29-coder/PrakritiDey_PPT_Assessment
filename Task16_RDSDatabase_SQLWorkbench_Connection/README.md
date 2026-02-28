# AWS RDS MySQL Setup and Connection Guide

## Project Overview

In this project, I created a MySQL database using Amazon RDS and connected it to MySQL Workbench from my local machine.  
I also configured security groups properly to allow secure external access and performed basic SQL operations like creating databases, tables, and inserting data.

This project helped me understand how managed database services work in AWS and how cloud databases are accessed securely.

---

## Step 1: Creating the RDS MySQL Database

1. Logged in to the AWS Console.
2. Navigated to the RDS service.
3. Clicked on "Create Database".
4. Selected:
   - Engine: MySQL
   - Template: Free tier
5. Set:
   - Database instance identifier
   - Master username
   - Master password
6. Enabled Public Access.
7. Created the database and waited until the status became **Available**.

---

## Step 2: Configuring Security Group

After the database was created, I configured the security group to allow external access.

- Went to RDS → Connectivity & Security.
- Opened the attached security group.
- Added an inbound rule:
  - Type: MySQL/Aurora
  - Port: 3306
  - Source: My IP

This step was important to allow my local system to connect to the database securely.

---

## Step 3: Connecting with MySQL Workbench

1. Opened MySQL Workbench.
2. Created a new connection.
3. Entered:
   - Hostname: RDS endpoint
   - Port: 3306
   - Username: admin
   - Password: (master password)
4. Tested the connection successfully.
5. Connected to the database.

---

## Step 4: Performing Basic SQL Operations

After connecting successfully, I ran the following SQL commands:

### Show existing databases
```sql
SHOW DATABASES;
```

### Create a new database
```sql
CREATE DATABASE mydb;
```

### Use the database
```sql
USE mydb;
```

### Create a table
```sql
CREATE TABLE students (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(50),
    age INT
);
```

### Insert data
```sql
INSERT INTO students (name, age)
VALUES ('Prakriti', 21);
```

### Retrieve data
```sql
SELECT * FROM students;
```

---

## Key Learnings

- Understanding Amazon RDS as a managed database service
- Configuring public access securely
- Working with security groups
- Connecting external applications to cloud databases
- Performing basic SQL operations
- Understanding how cloud networking affects database connectivity

---

## Technologies Used

- AWS RDS (MySQL)
- MySQL Workbench
- AWS Security Groups
- SQL

---

## Outcome

Successfully deployed a cloud-hosted MySQL database using Amazon RDS and connected it securely from my local machine.  
Performed database creation, table creation, data insertion, and retrieval operations.

This project strengthened my understanding of cloud databases and AWS networking concepts.
