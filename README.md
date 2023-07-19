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


### Install Sequlize 
- Follow the steps below to install sequelize
- By default Seqelize will create config.json file, change the extension to config.js
- If using DB cluster, we need to make SSL connection to the cluster. Add the follow code in config.js file
  ```
  "development": {
    "username": process.env.USER_NAME_D,
    "password": process.env.DB_PASSWORD_D,
    "database": process.env.DB_NAME_D,
    "host": process.env.DB_HOST_D,
    "dialect": process.env.DB_DIALECT_D,
    logging: false,
    port : process.env.DB_PORT_D,
    dialectOptions: {
      ssl: {
        require: true, // This will help you. But you will see nwe error
        rejectUnauthorized: false // This line will fix new error
      }
    },
    pool: {
      max: 10,
      min: 0,
      acquire: 30000,
      idle: 10000
    }
  }
  ```
  

### Common Model Queries 
- [LINK](https://sequelize.org/docs/v6/core-concepts/model-querying-basics/)
- By defaut index.js file in Models will be created, which can be used to work with all the models we define.
- While using model querying 





