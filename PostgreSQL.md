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

- Switch User and Logon to the PostgreSQL Command-Line
```bash
sudo -u postgres psql
```

- Restart PostgreSQL Service
```
sudo service postgresql restart
```
