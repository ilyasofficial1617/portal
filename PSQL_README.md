# How to Install PSQL
## linux

open the terminal and type in
```bash
sudo apt-get update 
sudo apt-get install postgresql postgresql-contrib
```

## windows
Download the installer from 
    https://www.enterprisedb.com/downloads/postgres-postgresql-downloads
and follow the installation process, if asked fill `5432` in port configuration

# How to Configure the Database
## linux
Create `systersdb` database, where `systersdb` might be any suitable name.

```bash
sudo -i -u postgres
createuser <anyname e.g. alice> --pwprompt
psql
CREATE DATABASE systersdb;
\c systersdb;
GRANT ALL PRIVILEGES ON DATABASE systersdb to <the name>;
```

Fill in the database details in `systers_portal/settings/dev.py`.

## windows
Create `systersdb` database, where `systersdb` might be any suitable name.
Open the SQL Shell for postgresql from the windows start menu or wherever accessible

```bash
Server [localhost]:  Just press enter, leave this empty
Database [postgres]: Just press enter, leave this empty
Port [5432]: This is the default port just press enter, leave this empty
Username [postgres]: This is the default username just press enter, leave this empty
Password for user postgres: Input password you created during installation and press enter
CREATE USER <anyname you want e.g systers> WITH PASSWORD <any password>;
CREATE DATABASE systersdb;
\c systersdb;
GRANT ALL PRIVILEGES ON systersdb TO <username created above>;
```

Fill in the database details in `systers_portal/settings/dev.py`.
