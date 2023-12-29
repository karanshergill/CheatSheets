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
```
psql -c "alter user postgres with password 'my00pass'"
```

- Switch User and Logon to the PostgreSQL Command-Line
```bash
sudo -u postgres psql
```

- Restart PostgreSQL Service
```
sudo service postgresql restart
```

#### Create a Database User and Database
```
postgres@msi:~$ createuser pgdbuser
postgres@msi:~$ createdb recondb -O pgdbuser
postgres@msi:~$ psql recondb
psql (16.1 (Debian 16.1-1))
Type "help" for help.

recondb=#
```
![image](https://github.com/karanshergill/CheatSheets/assets/83878909/37741607-69ea-4af1-819c-e3818a6584a6)

- Change the Role and Password
```
recondb=# alter user pgdbuser with password 'kali';
ALTER ROLE
recondb=# \q
postgres@msi:~$
```
![image](https://github.com/karanshergill/CheatSheets/assets/83878909/e72aa482-773f-4db1-a362-62d5136123c0)
