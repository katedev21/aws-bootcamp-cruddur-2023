# Week 4 — Postgres and RDS
check aws 
`aws sts get-caller-identity`

To connect to psql via the psql client cli tool remember to use the host flag to specific localhost.

`psql -Upostgres --host localhost`


Common PSQL commands:

```sql
\x on -- expanded display when looking at data
\q -- Quit PSQL
\l -- List all databases
\c database_name -- Connect to a specific database
\dt -- List all tables in the current database
\d table_name -- Describe a specific table
\du -- List all users and their roles
\dn -- List all schemas in the current database
CREATE DATABASE database_name; -- Create a new database
DROP DATABASE database_name; -- Delete a database
CREATE TABLE table_name (column1 datatype1, column2 datatype2, ...); -- Create a new table
DROP TABLE table_name; -- Delete a table
SELECT column1, column2, ... FROM table_name WHERE condition; -- Select data from a table
INSERT INTO table_name (column1, column2, ...) VALUES (value1, value2, ...); -- Insert data into a table
UPDATE table_name SET column1 = value1, column2 = value2, ... WHERE condition; -- Update data in a table
DELETE FROM table_name WHERE condition; -- Delete data from a table
```

The command to import:

`psql cruddur < db/schema.sql -h localhost -U postgres`

Get into postgres without re typing credentials
`postgres://postgres:password@localhost:5432/cruddur`

`export CONNECTION_URL="postgres://postgres:password@localhost:5432/cruddur"`

for fast access into env
`psql $CONNECTION_URL`

sed allows us to manipulate database
`NO_DB_CONNECTION_URL=$(sed 's/\/cruddur//g' <<<"$CONNECTION_URL")`



