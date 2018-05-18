# How to Install PSQL
## Debian / Ubuntu

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
## Debian / Ubuntu

Create the `systersdb` database.

```bash
CREATE DATABASE systersdb;
CREATE USER systersdbadmin IDENTIFIED BY ENCRYPTED PASSWORD 'yourpass';
GRANT ALL PRIVILEGES ON DATABASE systersdb to systersdbadmin;
```

Fill in the database details in `systers_portal/settings/dev.py`.

## windows
Create `systersdb` database, where `systersdb` might be any suitable name.
Open the SQL Shell for postgresql from the windows start menu or wherever accessible

```
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


Reference
[Django Girls'](http://djangogirls.org) ebook,
[Tutorials Extension](http://djangogirls.org/resources/), is a reference.
The info is also on [Django Girls GitHub repository](https://github.com/DjangoGirls/tutorial-extensions/blob/master/en/optional_postgresql_installation/README.md).

