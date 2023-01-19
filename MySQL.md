# MySQL
SQL can be used to perform the following actions:

- Retrieve data
- Update data
- Delete data
- Create new tables and databases
- Add / remove users
- Assign permissions to these users

---

#### Login to MySQL database (Local Host)
`▶ mysql -u root -p` or `▶ mysql -u root -p<password>`

#### Login to MySQL database (Remote Host)
`▶ mysql -u root -h database.example.com -P 3306 -p` or `▶ mysql -u root -h database.example.com -P 3306 -p<password>`

Note: Using the password directly in the command should be avoided, as it could lead to the password being kept in logs and terminal history.

---

#### Create a new database
`▶ CREATE DATABASE <database_name>;`

#### Use a database
`▶ USE <database_name>`;

#### Retrieve all exiting databases
`▶ SHOW DATABASES;`
 
---

#### Create a table with colums
```
▶ CREATE TABLE users (
  ▶ id INT,
  ▶ username VARCHAR(100),
  ▶ password VARCHAR(100),
  ▶ pin INT(10)
  ▶ date_of_joining DATETIME
    );
```

#### Properties/ Data Types of tables and colums
```
▶ id INT NOT NULL AUTO_INCREMENT;
▶ PRIMARY KEY (id)
```
 - `AUTO INCREMENT`- automatically increments the id by one every time a new item is added to the table.
 - `PRIMARY KEY` - integer value used to uniquely identify each record in the table.


---
