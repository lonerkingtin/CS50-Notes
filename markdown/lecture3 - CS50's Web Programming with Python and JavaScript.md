# Flask - Lecture 3 - cs50's web programming with python and javascript

## Databases

- we are talking about relational databases (data inside table is related to one another), which means storing data inside a table.

- we are using sql to query the database. sql is a language that allows us to interact with databases.

- this class we are using a database known as PostgreSQL.

1. first we create a database
2. then we create tables inside a database.
3. when creating a table we need to decide `what kind of data` that table is going to hold.

## Data Types

- INTEGER
- DECIMAL
- SERIAL (specific to PostgreSQL, similar to integer but increments automatically whenever you add a new row to the table.)
- VARCHAR (it stands for variable length of characters, )
- TIMESTAMP (date and time)
- BOOLEAN (True or False)
- ENUM (one of a finite number of discrete possible values)
- ...

## How to create a Table in Postgres

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
INSERT INTO flights (origin, destination, duration) VALUES ('Istanbul', 'Tokyo', 700);
INSERT INTO flights (origin, destination, duration) VALUES ('New York', 'Paris', 435);
INSERT INTO flights (origin, destination, duration) VALUES ('Moscow', 'Paris', 245);
INSERT INTO flights (origin, destination, duration) VALUES ('Lima', 'New York', 455);
```

| ID | origin | destination | duration |
|---|---|---|---|
| 1  | New York | London | 415 |
| 2  | shanghai | Paris | 760 |
| 3  | Istanbul | Tokyo | 700 |
| 4  | New York | Paris | 435 |
| 5  | Moscow | Paris  | 245 |
| 6  | Lima | New York | 455 |

## SELECT

- select all rows from the table.

 ```sql
SELECT * FROM flights;
 ```

- select specific columns from the table.

 ```sql
 SELECT origin, destination FROM flights;
 ```

---
 Note:

- select statement restrict columns.
- where clause restrict rows.

---

- select * from flights refer that we are selecting all the columns, where clause restrict rows.

```sql
SELECT * FROM flights WHERE id=3;
```

- similar to that, it selects the row where origin = 'New York'.

```sql
SELECT * FROM flights WHERE origin = 'New York';
```

- you can also use comparison operators in where clause.

```sql
SELECT * FROM flights WHERE duration > 500;
```

- you can also use boolean expression in where clause to retrieve specific rows.

```sql
SELECT * FROM flights WHERE destination = 'paris' AND duration > 500;
```

```sql
SELECT * FROM flights WHERE destination = 'paris' OR duration > 500;
```

## Functions

- SUM (used to find the sum value)
- COUNT (counts number of rows returned from the database)
In colloquial language, an average is a single number taken as representative of a list of numbers.
- MIN (used to find the minimum value)
- MAX (used to find the largest value)
- AVG (used to find the average)
- ...

```sql
SELECT AVG(duration) FROM flights;
```

```sql
SELECT AVG(duration) FROM flights WHERE origin = 'New York';
```

```sql
SELECT COUNT(*) FROM flights
```

```sql
SELECT MIN(duration) FROM flights;
```

```sql
SELECT MAX(duration) FROM flights;
```

## IN keyword

- using IN keyword, we can match with range of possible values.

```sql
SELECT * FROM flights WHERE origin IN ('New York', 'Lima');
```

## LIKE keyword

- using LIKE keyword, we can search for specific pattern in a column.

```sql
SELECT * FROM flights WHERE origin LIKE '%a%';
```

## UPDATE

```sql
UPDATE flights SET duration = 430 WHERE origin = 'New York' AND destination = 'London';
```

## DELETE

```sql
DELETE FROM flights WHERE destination = 'Tokyo';
```

## MULTIPLE QUERIES

```sql
SELECT *FROM flighs LIMIT 2;
```

```sql
SELECT * FROM flights ORDER BY duration ASC;
```

LIMIT (it restricts number of rows retrieved from database)
ORDER BY (it orders the rows by column value. default is asc order)
ASC (Ascending order)
DESC (Descending order)

---

In general terms, Ascending means smallest to largest, 0 to 9, and/or A to Z and Descending means largest to smallest, 9 to 0, and/or Z to A.

---

To get three shortest flight from the database:

```sql
SELECT * FROM flights ORDER BY duration Asc LIMIT 3;
```

To find most popular place based on number of flights:

```sql
SELECT origin, COUNT(*) FROM flights GROUP BY origin;
```

### GROUP BY

- group by is used in conjunction with aggregate functions such as count, sum, min, max, avg to group the resulting rows by column value.

```sql
SELECT origin, COUNT(*) FROM flights GROUP BY origin HAVING COUNT(*) > 1;
```

## FOREIGN KEY

- for the most of the cases, we will create multiple tables inside the database and establish relationships between them.

|id|origin|origin_code|destination|destination_code|duration|
|---|---|---|---|---|---|
|1|New York|JFK|London|LHR|415|
|2|shanghai|PVG|Paris|CDG|760|
|3|Istanbul|IST|Tokyo|NRT|700|
|4|New York|JFK|Paris|CDG|435|
|5|Moscow|SVO|Paris|CDG|245|
|6|Lima|LIM|New York|JFK|455|

### Flights

|id|origin_id|destination_id|duration|
|---|---|---|---|
|1|1|4|415|
|2|2|7|760|
|3|3|8|700|
|4|1|7|435|
|5|5|7|245|
|6|6|1|435|

### Location

|id|code|name|
|---|---|---|
|1|JFK|New York|
|2|PVG|Shanghai|
|3|IST|Istanbul|
|4|LHR|London|
|5|SVO|Moscow|
|6|LIM|Lima|
|7|CDG|Paris|
|8|NRT|Tokyo|

### Passengers

|id|name|flight_id|
|---|---|---|
|1|Alice|1|
|2|Bob|1|
|3|Charlie|2|
|4|Dave|2|
|5|Erin|4|
|6|Frank|6|
|7|Grace|6|


 ```sql

```