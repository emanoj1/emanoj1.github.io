---
layout: post
date: 2024-05-14 20:45:00 +1000
title: 9. Deciphering a PostgreSQL statement
tag: postgresql
---

In this post, we try to understand each line of a simple PostgreSQL statement.

**What is PostgreSQL?**

Amazon Web Services (AWS) has a good explanation: "PostgreSQL is an advanced, enterprise-class open-source relational database that supports both SQL (relational) and JSON (non-relational) querying. 
It is a highly stable database management system backed by more than 20 years of community development.   

Read more here: [What is PostgreSQL?](https://aws.amazon.com/rds/postgresql/what-is-postgresql).   
The official site is here: [postgresql.org](https://www.postgresql.org/)  

So, let's look at the statement in question:  

```
CREATE TABLE HOUR_ASSIGNMENTS(
hour_assignment_id serial PRIMARY KEY,
project_id integer NOT NULL,
employee_id integer NOT NULL,
hours decimal (6,2) NOT NULL CHECK (hours > 0),
FOREIGN KEY(project_id) REFERENCES PROJECTS(proj_id) ON DELETE CASCADE,
FOREIGN KEY(employee_id) REFERENCES EMPLOYEES(emp_id) ON DELETE CASCADE);
```

Let's break down each line of the SQL statement:  

1. `CREATE TABLE HOUR_ASSIGNMENTS(`:
   - This begins the creation of a new table named `HOUR_ASSIGNMENTS`.  


2. `hour_assignment_id serial PRIMARY KEY,`:
   - This defines a column named `hour_assignment_id` as the primary key for the table. The `serial` data type is typically used for auto-incrementing integer columns in PostgreSQL databases, meaning each new row inserted into the table will automatically generate a unique value for this column.  


3. `project_id integer NOT NULL,`:
   - This defines a column named `project_id` as an integer type, which cannot contain NULL values.  


4. `employee_id integer NOT NULL,`:
   - This defines a column named `employee_id` as an integer type, which cannot contain NULL values.  


5. `hours decimal (6,2) NOT NULL CHECK (hours > 0),`:
   - This defines a column named `hours` as a decimal type with a precision of 6 digits and a scale of 2 (allowing for values with up to 4 digits before the decimal point and 2 digits after). The `NOT NULL` constraint ensures that this column cannot contain NULL values. The `CHECK` constraint ensures that the value of `hours` must be greater than 0.  


6. `FOREIGN KEY(project_id) REFERENCES PROJECTS(proj_id) ON DELETE CASCADE,`:
   - This creates a foreign key constraint on the `project_id` column, referencing the `proj_id` column in the `PROJECTS` table. The `ON DELETE CASCADE` option specifies that if a row in the `PROJECTS` table is deleted, all corresponding rows in the `HOUR_ASSIGNMENTS` table with matching `project_id` values will also be deleted.  


7. `FOREIGN KEY(employee_id) REFERENCES EMPLOYEES(emp_id) ON DELETE CASCADE);`:
   - This creates a foreign key constraint on the `employee_id` column, referencing the `emp_id` column in the `EMPLOYEES` table. Similarly, the `ON DELETE CASCADE` option specifies that if a row in the `EMPLOYEES` table is deleted, all corresponding rows in the `HOUR_ASSIGNMENTS` table with matching `employee_id` values will also be deleted.  


In summary, this SQL statement creates a table named `HOUR_ASSIGNMENTS` with columns for assignment IDs, project IDs, employee IDs, and hours worked. It includes constraints to ensure data integrity, such as not allowing NULL values for certain columns and enforcing referential integrity between this table and other tables (`PROJECTS` and `EMPLOYEES`) through foreign key constraints with cascading delete behavior.  

