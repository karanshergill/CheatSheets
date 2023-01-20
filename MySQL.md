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

#### Create a table with some columns
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

#### MySQL Statements
- `SELECT` - retrive records from the table.
- `INSERT` - add records to the given table.
- `DROP` - permanently delete tables and databases.
- `ALTER` - change the name of any table and any of its fields or to delete or add a new column to an existing table.
- `UPDATE` - used to update specific records within a table, based on certain conditions.

**SELECT** Syntax:
```
▶ SELECT * FROM table_name; # select all(*) columns from the given table
   OR
▶ SELECT column1, column2 FROM table_name; # select specific columns from the given table
```

**INSERT** Syntax:
```
▶ INSERT INTO table_name(column2, column3, ...) VALUES (column2_value, column3_value, ...);
```
- `*` - wildcard character, which means everything.
- `column2, column3` - name of the columns in the table.
- `column2_value, column3_value` - values of the records to be inserted.
- `NOT-NULL` - values for the columns with this constraint cannot be left blank.
- `DEFAULT` - values for the columns with this constraint can be left blank.


**DROP** Syntax:
```
▶ DROP TABLE table_name;
```
- permanentlt deletes the table `table_name`.

**ALTER** Syntax:
```
▶ ALTER TABLE table_name ADD newColumn_name INT;
```
- creates a new column `newColumn_name` with the data types as integer within the given table `table_name`.

```
▶ ALTER TABLE table_name RENAME COLUMN newColumn_name TO NewColumn_Name;
```
- renames the column `newColumn_name` to `NewColumn_Name` within the given `table_name`.

```
▶ ALTER TABLE table_name MODIFY NewColumn_Name DATE;
```
- modifies the data type of the given column `NewColumn_Name` to date within the given `table_name`.

```
▶ ALTER TABLE table_name DROP column_name;
```
- permanently delets the column from the given table name.

**UPDATE** Syntax:
```
▶ UPDATE table_name SET column1=newvalue1, column2=newvalue2, ... WHERE <condition>;
```
- `WHERE` - use with UPDATE, in order to specify the column name/s or a condition.

#### Other Learning Resources:
- [MySQL Tutorial](https://www.mysqltutorial.org/)
- [Everything You Need To Know About SQL Injection](https://www.sqlinjection.net/)
- [MySQL Security Documentation](https://dev.mysql.com/doc/refman/8.0/en/security-guidelines.html)
