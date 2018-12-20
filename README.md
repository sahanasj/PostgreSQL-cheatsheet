# PostgreSQL-cheatsheet
PostgreSQL command line cheatsheet

The PostgreSQL cheat sheet provides with the common PostgreSQL commands and statements that enable you to work with PostgreSQL quickly and effectively.

## PostgreSQL commands
1. Access the PostgreSQL server from psql with a specific user:

**psql -U [username];**

For example, the following command uses the postgres user to access the PostgreSQL database server: <br>
**$ psql -U postgres**

Some interesting flags (to see all, use -h or --help depending on your psql version):

- -E: will describe the underlaying queries of the \ commands (cool for learning!)
- -l: psql will list all databases and then exit (useful if the user you connect with doesn't has a default database, like at AWS RDS)

Most \d commands support additional param of __schema__.name__ and accept wildcards like *.*

- \q: Quit/Exit
- \c __database__: Connect to a database
- \d __table__: Show table definition including triggers
- \l: List databases
- \dy: List events
- \df: List functions
- \di: List indexes
- \dn: List schemas
- \dt *.*: List tables from all schemas (if *.* is omitted will only show SEARCH_PATH ones)
- \dv: List views
- \df+ __function__ : Show function SQL code.
- \x: Pretty-format query results instead of the not-so-useful ASCII tables
- \copy (SELECT * FROM __table_name__) TO 'file_path_and_name.csv' WITH CSV: Export a table as CSV

**User Related:**

- \du: List users
- \du __username__: List a username if present.
- create role test1: Create a role with an existing username
- create role test2 noinherit login password 'TooManySecrets';: Create a role with username and password.
- set role test;: Change role for this session to test1.
- grant test2 to test1;: Allow test1 to set its role as test2.

**Performance basics:**
- EXPLAIN query: see the query plan for the given query
- EXPLAIN ANALYZE query: see and execute the query plan for the given query
- ANALYZE [table]: collect statistics

**Configuration - Service management commands:**
- sudo service postgresql stop
- sudo service postgresql start
- sudo service postgresql restart

**Reference** <br>
[PostgreSQL Cheat Sheet](http://www.postgresqltutorial.com/postgresql-cheat-sheet/)
 <br>
 [PSQL](https://gist.github.com/Kartones/dd3ff5ec5ea238d4c546)
