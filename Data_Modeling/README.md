# PostgreSQL Setup for database backend

### About PostgreSQL

- PostgreSQL is an ACID-compliant Object Relational Database Management System
- Due to its first-class support for JSON, Postgres is often a good alternative to “No-SQL” databases like MongoDB


#### Installing Postgres 
`brew install postgresql`
#### Checking the version
`postgres -V`

## Configuring Postgres
- Start by using the psql utility, which is a utility installed with Postgres that lets you carry out administrative functions without needing to know their actual SQL commands.
`psql postgres`
- enter a command to see what users are installed
`postgres=# \du`

### Creating Users
- Postgres doesn’t actually directly manage users or groups, like most standard permission models do. Instead, it directly manages what it calls roles.
- There are two main ways to do this: 1. Execute SQL query 2. Use the createuser utility
##### 1. CREATE ROLE with psql
`postgres=# CREATE ROLE username WITH LOGIN PASSWORD 'quoted password' [OPTIONS];` -- no any permissions
`postgres=# ALTER ROLE patrick CREATEDB; ` -- add the CREATEDB permission to the user
##### 2. The createuser utility
--  createuser: creates a user
--  createdb: creates a database
-- dropuser: deletes a user
-- dropdb: deletes a database
-- postgres: executes the SQL server itself (we saw that one above when we checked our Postgres version!)
-- pg_dump: dumps the contents of a single database to a file
-- pg_dumpall: dumps all databases to a file
-- psql: PostgreSQL interactive terminal

### Creating a Database
`postgres=> CREATE DATABASE songs;`
`\list`: lists all the databases in Postgres
`\connect`: connect to a specific database
`\dt`: list the tables in the currently connected database
##### ALTER DATABASE
`postgres=> ALTER DATABASE songs RENAME TO albums`
`postgres=> \q`

### GUIs for PostgreSQL on MacOSX
pgAdmin (https://www.pgadmin.org/)


![](https://pandao.github.io/editor.md/examples/images/8.jpg)


