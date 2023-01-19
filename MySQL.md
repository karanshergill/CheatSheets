# MySQL Quick Reference (Cheet Sheat)

**MySQL can be used to perform the following actions:**
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
    id INT NOT NULL AUTO_INCREMENT,
    username VARCHAR(24) UNIQUE NOT NULL,
    password VARCHAR(100) NOT NULL,
    pin INT(8) NOT NULL,
    date_of_registration DATETIME DEFAULT NOW(),
    PRIMARY KEY (id)
    );
```

#### Defining data types of the table and its colums
 - `VARCHAR(24)` - a string with a length of 24 characters *(maximum length can be upto 65535 characters)*.
 - `INT(8)` - an integer with a length of 8 characters *(maximum value can be upto 10 characters)*.
 - `UNIQUE` - constraint to ensures that the inserted item are always unique.
 - `NOT NULL` - constraint ensures that a particular column is never left empty 'i.e., required field'.
 - `DEFAULT` - used to specify the default value *(automatically insterted)*.
 - `AUTO INCREMENT`- automatically increments the id by one every time a new item is added to the table.
 - `PRIMARY KEY` - integer value used to uniquely identify each record in the table.
 - `NOW()` - returns the current date and time.

---

#### Other Learning Resources:
- [MySQL Tutorial](https://www.mysqltutorial.org/)
- [Everything You Need To Know About SQL Injection](https://www.sqlinjection.net/)
- [MySQL Security Documentation](https://dev.mysql.com/doc/refman/8.0/en/security-guidelines.html)
