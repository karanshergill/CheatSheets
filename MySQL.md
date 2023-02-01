# MySQL Quick Reference (Cheet Sheat)

**MySQL can be used to perform the following actions:**
- Retrieve data
- Update data
- Delete data
- Create new tables and databases
- Add / remove users
- Assign permissions to these users

---
## Login

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

*Note: String and date data types should be surrounded by single quote (') or double quotes ("), while numbers can be used directly.*

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

---

#### Query Results

Sort Results
```
▶ SELECT * FROM users ORDER BY password;
```
- `ORDER BY` - sort the results of any query using ORDER BY and specifying the column to sort by (by default sorting is done in ascending order).

```
▶ SELECT * FROM users ORDER BY password DESC;
```
- `ASC` or `DESC` - sort the results by ascending or descending order.

```
▶ SELECT * FROM users ORDER BY password DESC, id ASC;
```
- `ASC` and `DESC`- sort by multiple columns, to have a secondary sort for duplicate values in one column


Limit Results
```
▶ SELECT * FROM users LIMIT 2;
```
- `LIMIT <integer>` - limits the number of results returned by the query to the specified integer value.

```
▶ SELECT * FROM users LIMIT 1, 2;
```
- `LIMIT <integer1>, <integer2>` - sets the offset, will return the records specified within the range. The offset marks the order of the first record to be included, starting from 0.

Filter Searches/ Specific Results/ Patterns
```
▶ SELECT * FROM table_name WHERE <condition>;
```
- `WHERE` -  filter or search for specific data.
Examples:
```
▶ SELECT * FROM users WHERE id > 1;
▶ SELECT * FROM users WHERE username = 'admin';
```

```
▶ SELECT * FROM logins WHERE username LIKE 'admin%';
```
- `LIKE` - enabling selecting records by matching a certain pattern.
- `%` - acts as a wildcard and matches all characters after admin. It is used to match zero or more characters.

```
▶ SELECT * FROM logins WHERE username like '___';
```
- `_` - used to match exactly one character. Three underscores represent three characters.

---

#### MySQL Operators
 - Logical Operators - `AND`, `OR`, `NOT`
 - Logical Symbol Operators - `&&`, `||`, `!=` (AND, OR, NOT respectively.)

**AND**
```
▶ SELECT 1 = 1 AND 'test' = 'test';
```
 - The AND operator takes in two conditions and returns true or false based on their evaluation: condition1 `AND` condition2. The result of the AND operation is true if and only if both condition1 and condition2 evaluate to true. In MySQL any non-zero value is considered true, and it usually returns the value 1 to signify true. 0 is considered false.

**OR**
```
▶ SELECT 1 = 1 OR 'test' = 'abc';
```
 - The OR operator takes in two expressions and returns true when at least one of them evaluates to true

**NOT**
```
▶ SELECT NOT 1 = 1;
```
 - The NOT operator simply toggles a boolean value 'i.e. true is converted to false and vice versa'.

**UNION**
```
▶ SELECT * FROM users UNION SELECT * FROM logins;
```
- The Union clause is used to combine results from multiple SELECT statements.
- A UNION statement can only operate on SELECT statements with an equal number of columns.
- An attempt to UNION two queries that have results with a different number of columns will return an error.
---

#### Operator Precedence
 - Division (/), Multiplication (\*), and Modulus (%)
 - Addition (+) and subtraction (-)
 - Comparison (=, >, <, <=, >=, !=, LIKE)
 - NOT (!)
 - AND (&&)
 - OR (||)

---
#### Other Learning Resources:
- [MySQL Tutorial](https://www.mysqltutorial.org/)
- [Everything You Need To Know About SQL Injection](https://www.sqlinjection.net/)
- [MySQL Security Documentation](https://dev.mysql.com/doc/refman/8.0/en/security-guidelines.html)
