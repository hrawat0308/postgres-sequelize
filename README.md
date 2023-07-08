# Postgres-Sequelize

### Install Postgres on Ubuntu
- Go to the official website and you can run the given commands in your terminal [click here](https://www.postgresql.org/download/linux/ubuntu/)
- ```
  # Create the file repository configuration:
    sudo sh -c 'echo "deb http://apt.postgresql.org/pub/repos/apt $(lsb_release -cs)-pgdg main" > /etc/apt/sources.list.d/pgdg.list'

  # Import the repository signing key:
    wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add -

  # Update the package lists:
    sudo apt-get update

  # Install the latest version of PostgreSQL.
  # If you want a specific version, use 'postgresql-12' or similar instead of 'postgresql':
    sudo apt-get -y install postgresql
  ```
  - Once all commands are executed,  Postgres server must be running on your system.

### To interact with Postgres you can use psql client :
  1. open terminal
  2. ```sudo -i -u postgres```
  3. `psql`
  4. to exit - ```\q```
  5. create database - `createdb mydb`
  6. use database - `psql -d mydb`
  7. get information about connection - `\conninfo`
  8. to view all databases - `\l`
  
### Install pgAdmin a GUI for postgres
- [link](https://www.pgadmin.org/download/pgadmin-4-apt/)
- follow the commands given in above mentioned link.
- open pgAdmin application and go to register server
- set up a password for user `postgres`
  - `sudo -i -u postgres`
  - `psql`
  - `\password postgres`
- enter this password in pgAdmin while registering a server. Click save
