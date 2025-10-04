## **Insert, Update, and Delete Data in a Database**
### **Overview**

This hands-on AWS lab demonstrates how to insert, update, delete, and import data in a relational database using Structured Query Language (SQL).
The lab uses an Amazon EC2 Command Host connected to a MySQL database containing the world schema with three tables: city, country, and countrylanguage.

At the end of this lab, you will understand how to perform data manipulation operations (DML) such as INSERT, UPDATE, DELETE, and IMPORT.

### **Objectives & Learning Outcomes**

After completing this lab, I was able to:

Insert rows into a database table using the INSERT statement

Modify existing rows using the UPDATE statement

Delete data using the DELETE statement

Import rows from a backup file using SQL scripts

Understand the relationship between tables in a relational database

### **Architecture**
<p align="center"> <img src="architecture/database-lab-architecture.png" alt="Database Architecture" width="650"/> </p>

### **Architecture Summary:**

User (Lab Student) connects via AWS Management Console

Amazon EC2 Command Host acts as the SQL client terminal

Amazon RDS MySQL Database hosts the world database

SQL commands (INSERT, UPDATE, DELETE, and IMPORT) are executed from the EC2 instance to manipulate data within the RDS instance.
