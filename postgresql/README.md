# Install PostgreSQL

[Install PostgreSQL](https://www.rosehosting.com/blog/how-to-install-postgresql-9-6-on-ubuntu-20-04/)

## Configure Postgres User,


```zsh
$ sudo su - postgres
$ psql -U postgres -c "CREATE USER jissmon WITH PASSWORD 'pass890'; ALTER USER jissmon WITH SUPERUSER;"
psql -U postgres -c "CREATE DATABASE gessit;"
psql -U postgres -c "ALTER ROLE postgres SET search_path TO healthelink;"
```

## Connect to Database

```zsh
postgres=# \connect gessit
```

# Completely Uninstall Postgresql

[Remove Postgresql Completely](https://kb.objectrocket.com/postgresql/how-to-completely-uninstall-postgresql-757)


### Use apt-get to remove Postgresql

```zsh
sudo apt-get --purge remove postgresql
sudo apt-get purge postgresql*
sudo apt-get --purge remove postgresql postgresql-doc postgresql-common
```

### Search for all the package names installed that contain the sub-string postgres:

```zsh
dpkg -l | grep postgres
```

### Remove Specific postgresql package(Version 9.6):

```zsh
sudo apt-get --purge remove postgresql-9.6
```

### Remove all of the PostgreSQL data and directories:

```zsh
sudo rm -rf /var/lib/postgresql/
sudo rm -rf /var/log/postgresql/
sudo rm -rf /etc/postgresql/
sudo rm -rf /etc/postgresql-common
sudo rm -rf /etc/apt/sources.list.d/postgresql-pgdg.list 
```

### Check all postgresql packages and directoreis were removed:

```zsh
dpkg -l | grep postgres
sudo su - postgres 
```