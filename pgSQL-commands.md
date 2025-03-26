
- [[#Change to the default `postgres` user and run `psql`]]
- [[#Connect to database]]
	- [[#Same host]]
	- [[#Different host database]]
- [[#List all databases - ` l`]]
- [[#Switch to another database - ` c`]]
- [[#List database tables - ` dt`]]
- [[#Describe a table - ` d`]]
- [[#List all schemas - ` dn`]]
- [[#List users and their roles - ` du`]]
- [[#Retrieve a specific user - ` du`]]
- [[#List all functions - ` df`]]
- [[#List all views - ` dv`]]
- [[#Save query results to a file - ` o`]]
- [[#Run commands from a file - ` i`]]
- [[#Quit psql]]

---

### Change to the default `postgres` user and run `psql`
```bash
sudo -i -u postgres
psql
```

---

### Connect to database
##### Same host
```
psql -d <db-name> -U <username> -W

// example
psql -d tutorials_db -U admin -W
```
The above command includes three flags:

- `-d` - specifies the name of the database to connect to
- `-U` - specifies the name of the user to connect as
- `-W` - forces pgSQL to ask for the user password before connecting to the database
---

#### Different host database

In the cases where your database is hosted somewhere else, you can connect as follows:

```
psql -h <db-address> -d <db-name> -U <username> -W

//example
psql -h my-psql-db.cloud.neon.tech -d tutorials_db -U admin -W
```

The `-h` flag specifies the host address of the database.

---

### List all databases - `\l`

In many cases, you will work with more than one database. You can list all the available databases with the following command:

```
\l
```
---
#### Switch to another database - `\c`

You can also switch to another database with the following command:

```
\c <db-name>

// example
\c tutorials_db
```

The below image illustrates the result after running the command.

---
#### List database tables - `\dt`

Let's consider you want to see all the tables from the database. You can list all database tables as follows:

```
\dt
```

---
### Describe a table - `\d`

pgSQL also has a command that lets you see the table's structure.

```
\d <table-name>

// example
\d tutorials
```

---
### List all schemas - `\dn`

The `\dn` pgSQL command lists all the database schemas.

---
### List users and their roles - `\du`


Sometimes, you might need to change the user. PostgreSQL has a command that lists all the users and their roles.
```
\du
```

---
### Retrieve a specific user - `\du`

You can also retrieve information about a specific user with the following command:

```
\du <username>

//example
/du postgres
```

---
### List all functions - `\df`

You can list all the functions from your database with the `\df` command.

---
### List all views - `\dv`

The `psql` interface enables you to list all the database views with the `\dv` command.

---
### Save query results to a file - `\o`

There might be cases where you want to analyze the result of a query at a later time. Or two compare two query results. The `psql` interface allows you to do that.

You can save query results in a file as follows:

```
\o <file-name>

// example
\o query_results
...run the psql commands...
\o - stop the process and output the results to the terminal again
```

---
### Run commands from a file - `\i`

It's also possible to run commands from a file. For simple commands, it might not be the best solution. But when you want to run multiple commands and complex SQL statements, it helps a lot.

Create a `txt` file with the following content:

```
\l
\dt
\du
```

When you run the file, it should return a list of all:

- databases
- database tables
- users

---
### Quit psql
```
\q
```