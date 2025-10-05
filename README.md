## **Insert, Update, and Delete Data in a Database**

### **Overview**

This hands-on AWS lab demonstrates how to insert, update, delete, and import data in a relational database using Structured Query Language (SQL).
The lab uses an Amazon EC2 Command Host connected to a MySQL database containing the world schema with three tables: city, country, and countrylanguage.

At the end of this lab, you will understand how to perform data manipulation operations (DML) such as INSERT, UPDATE, DELETE, and IMPORT.

---

### **Objectives & Learning Outcomes**

After completing this lab, I was able to:

Insert rows into a database table using the INSERT statement

Modify existing rows using the UPDATE statement

Delete data using the DELETE statement

Import rows from a backup file using SQL scripts

Understand the relationship between tables in a relational database

---

### **Architecture**

<img width="500" height="500" alt="e85d12bb-b5f1-41f4-ae0e-c03cb6908983" src="https://github.com/user-attachments/assets/33427d10-8ae7-4156-be3a-45eeb8f9db78" />

---

### **Architecture Summary:**

User (Lab Student) connects via AWS Management Console

Amazon EC2 Command Host acts as the SQL client terminal

Amazon RDS MySQL Database hosts the world database

SQL commands (INSERT, UPDATE, DELETE, and IMPORT) are executed from the EC2 instance to manipulate data within the RDS instance.

---

### **Commands and Steps**

~~~bash
# Step 1: Connect to the MySQL database
sudo su
cd /home/ec2-user/
mysql -u root --password='re:St@rt!9'

# Step 2: View existing databases
SHOW DATABASES;

# Step 3: Verify existing tables
SELECT * FROM world.country;

# Step 4: Insert new rows into the country table
INSERT INTO world.country VALUES 
('IRL','Ireland','Europe','British Islands',70273.00,1921,3775100,76.8,75921.00,73132.00,'Ireland/Éire','Republic',1447,'IE'),
('AUS','Australia','Oceania','Australia and New Zealand',7741220.00,1901,18886000,79.8,351182.00,392911.00,'Australia','Constitutional Monarchy, Federation',135,'AU');

# Step 5: Verify inserted data
SELECT * FROM world.country WHERE Code IN ('IRL', 'AUS');

# Step 6: Update rows in the table
UPDATE world.country SET Population = 0;
SELECT * FROM world.country;

# Step 7: Update multiple columns
UPDATE world.country SET Population = 100, SurfaceArea = 100;
SELECT * FROM world.country;

# Step 8: Delete all rows in the table
SET FOREIGN_KEY_CHECKS = 0;
DELETE FROM world.country;
SELECT * FROM world.country;

# Step 9: Exit MySQL and import data from SQL file
QUIT;
ls /home/ec2-user/world.sql
mysql -u root --password='re:St@rt!9' < /home/ec2-user/world.sql

# Step 10: Reconnect and verify import
mysql -u root --password='re:St@rt!9'
USE world;
SHOW TABLES;
SELECT * FROM country;
SELECT * FROM city;
SELECT * FROM countrylanguage;
~~~

---
### **Screenshoots**

01_show_databases.png

<img width="759" height="470" alt="Screenshot 2025-10-04 082720" src="https://github.com/user-attachments/assets/b5d596b9-3412-40b5-8eee-8194f32a8a36" />

02_insert_data.png
<img width="1901" height="295" alt="Screenshot 2025-10-04 083202" src="https://github.com/user-attachments/assets/8956630a-bc9d-4090-b661-8418a603ac63" />

03_update_data.png
<img width="1894" height="493" alt="Screenshot 2025-10-04 083656" src="https://github.com/user-attachments/assets/209d0d1c-e5ef-4b95-a656-797d9383b97a" />

04_delete_data.png

<img width="549" height="213" alt="Screenshot 2025-10-04 083923" src="https://github.com/user-attachments/assets/d872f9d3-3100-4953-ada4-754f38ef128c" />

05_import_data_verify_table_final_out.png
<img width="1904" height="890" alt="Screenshot 2025-10-04 084738" src="https://github.com/user-attachments/assets/966627c3-2a91-4209-98c7-291ccae1d4b0" />

---

### **Tools Used**

Amazon EC2 (Command Host) – for SQL client operations

Amazon RDS (MySQL) – relational database hosting the world schema

AWS Systems Manager (Session Manager) – for secure terminal access

MySQL Command Line Interface – for running SQL queries

---

### **Key Takeaways**

Practiced the use of DML SQL commands (INSERT, UPDATE, DELETE)

Learned how to import large data sets using .sql files

Observed the effect of missing WHERE clauses in UPDATE and DELETE

Strengthened understanding of data manipulation within AWS-hosted MySQL environments

---

### **Author**

Amarachi Emeziem
Cloud Security & IT Support Specialist | AWS & Azure Certified

https://www.linkedin.com/in/amarachilemeziem/
---
