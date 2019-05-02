# Flask - Lecture 3 - cs50's web programming with python and javascript



## Databases

- we are talking about relational databases (data inside table is related to one another), which means storing data inside a table.

- we are using sql to query the database. sql is a language that allows us to interact with databases.

- this class we are using a database known as PostgreSQL. 



1. first we create a database
2. then we create tables inside a database.
3. when creating a table we need to decide `what kind of data` that table is going to hold.



## Data Types:

- INTEGER
- DECIMAL
- SERIAL (specific to PostgreSQL, similar to integer but increments automatically whenever you add a new row to the table.)
- VARCHAR (it stands for variable length of characters, )
- TIMESTAMP (date and time)
- BOOLEAN (True or False)
- ENUM (one of a finite number of discrete possible values)
- ...



## How to create a Table in Postgres?

```sql
CREATE TABLE flights (
	id SERIAL PRIMARY KEY,
    origin VARCHAR NOT NULL,
    destination VARCHAR NOT NULL,
    duration INTEGER NOT NULL
);
```

\d - to list all table 

\du - to list all roles (user)

\l - to list all database

## Constraints

- NOT NULL (column must have a value, else database will reject the row entry.)
- UNIQUE (the column value must be unique, for example, every user must have different username, so that should be unique. )
- PRIMARY KEY (that uniquely identifies a row in a table, mostly used as a ID)
- DEFAULT (insert default value into the column unless user provided another input.)
- CHECK (means the column only allow values that are > 50 or >100)
- ....

## INSERT

```sql
INSERT INTO flights (origin, destination, duration) VALUES ('New York', 'London', 415);
INSERT INTO flights (origin, destination, duration) VALUES ('shanghai', 'Paris', 760);
INSERT INTO flights (origin, destination, duration) VALUES ('Istanbul', 'Tokyo', 415);
INSERT INTO flights (origin, destination, duration) VALUES ('New York', 'Paris', 415);
INSERT INTO flights (origin, destination, duration) VALUES ('Moscow', 'Paris', 415);
INSERT INTO flights (origin, destination, duration) VALUES ('New York', 'London', 415);
INSERT INTO flights (origin, destination, duration) VALUES ('Lima', 'New York', 415);
```

 ## SELECT 

- select all rows from the table.
 ```sql
SELECT * FROM flights;
 ```
- select specific columns from the table.
 ```sql
 SELECT origin, destination FROM flights;
 ```
 Note:
- select statement restrict columns.
- where clause restrict rows.

```sql
SELECT * FROM flights WHERE id=3;
```

```sql
SELECT * FROM flights WHERE origin = 'New York';
```

```sql
SELECT * FROM flights WHERE duration > 500;
```

```sql
SELECT * FROM flights WHERE destination = 'paris' AND duration > 500;
```