### PostgreSQL CheatSheet

- Start PostgreSQL Server
```bash
sudo service postgresql start
```

- List PostgreSQL Configuration File
```bash
sudo -u postgres psql -c 'SHOW config_file'
```

- Switch to User "postgres"
```bash
sudo su -l postgres
```

- Change Password of User "postgres"
```bash
psql -c "alter user postgres with password 'my00pass'"
```

- Switch User and Logon to the PostgreSQL Command-Line
```bash
sudo -u postgres psql
```

- Restart PostgreSQL Service
```bash
sudo service postgresql restart
```

#### Create a Database User and Database
```bash
postgres@msi:~$ createuser pgdbuser
postgres@msi:~$ createdb recondb -O pgdbuser
postgres@msi:~$ psql recondb
psql (16.1 (Debian 16.1-1))
Type "help" for help.

recondb=#
```
![image](https://github.com/karanshergill/CheatSheets/assets/83878909/37741607-69ea-4af1-819c-e3818a6584a6)

- Change the Role and Password
```psql
recondb=# alter user pgdbuser with password 'kali';
ALTER ROLE
recondb=# \q
postgres@msi:~$
```
![image](https://github.com/karanshergill/CheatSheets/assets/83878909/e72aa482-773f-4db1-a362-62d5136123c0)

- List Databases
```bash
postgres@msi:~$ psql -l
                                                   List of databases
   Name    |  Owner   | Encoding | Locale Provider | Collate |  Ctype  | ICU Locale | ICU Rules |   Access privileges
-----------+----------+----------+-----------------+---------+---------+------------+-----------+-----------------------
 postgres  | postgres | UTF8     | libc            | C.UTF-8 | C.UTF-8 |            |           |
 recondb   | pgdbuser | UTF8     | libc            | C.UTF-8 | C.UTF-8 |            |           |
 template0 | postgres | UTF8     | libc            | C.UTF-8 | C.UTF-8 |            |           | =c/postgres          +
           |          |          |                 |         |         |            |           | postgres=CTc/postgres
 template1 | postgres | UTF8     | libc            | C.UTF-8 | C.UTF-8 |            |           | =c/postgres          +
           |          |          |                 |         |         |            |           | postgres=CTc/postgres
(4 rows)
```
![image](https://github.com/karanshergill/CheatSheets/assets/83878909/cee2bf05-b197-40ac-af54-2f740e70ac7e)


#### Connect to PgAdmin
- Modify the value of "listen_address" in `postgresql.conf` file.

```bash
nano /etc/postgresql/16/main/postgresql.conf
```
![image](https://github.com/karanshergill/CheatSheets/assets/83878909/bbba9fed-97eb-4641-aedf-693278806eec)

- The `pg_hba.conf` should have the below configuration.
```
nano /etc/postgresql/16/main/pg_hba.conf
```
![image](https://github.com/karanshergill/CheatSheets/assets/83878909/88548d4f-727e-463d-93d9-1ec72069f995)
