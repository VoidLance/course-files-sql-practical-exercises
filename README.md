# SQL Practical Exercises

An archive of hands-on SQL exercises completed as part of the ITonlinelearning
software developer course. The repository covers relational database design,
data manipulation, permissions, views, stored programs, triggers, cursors, and
error handling, with a separate Formula 1 data challenge.

## Why use this repository?

- Practise SQL against realistic, progressively more complex scenarios.
- Compare exercise briefs, written solutions, and executable SQL scripts.
- Explore both MySQL/MariaDB procedural SQL and a portable SQLite dataset.
- Use the included CSV and database files for query practice and experimentation.

This is a learning repository rather than a packaged application. Scripts are
provided as study material and may need to be adapted to your local database
version or execution environment.

## Contents

| Directory | Topics and resources |
| --- | --- |
| [`CreateTable/`](CreateTable/) | Relational design, `CREATE TABLE`, `ALTER TABLE`, constraints, indexes, temporary tables, and dropping tables. See [`exercises.md`](CreateTable/exercises.md). |
| [`EcommerceDatabase/`](EcommerceDatabase/) | Customers, products, orders, transactions, and foreign-key behaviour. See [`exercises.md`](EcommerceDatabase/exercises.md). |
| [`Student_Information_System/`](Student_Information_System/) | Users, grants, roles, revoking privileges, views, procedures, and functions. See [`exercises.md`](Student_Information_System/exercises.md) and [`manipulating.md`](Student_Information_System/manipulating.md). |
| [`Advanced_Database_Operations/`](Advanced_Database_Operations/) | Triggers, audit logs, cursors, dynamic SQL, and exception handlers. See [`exercises.md`](Advanced_Database_Operations/exercises.md). |
| [`F1 Challenge/`](F1%20Challenge/) | Formula 1 CSV data, a ready-to-query SQLite database, and the challenge brief. |

The module solution archives are retained alongside the written exercise notes.
The `.frm` and `.ibd` files are local MySQL/MariaDB data files and are not
intended to replace the SQL scripts.

## Getting started

### MySQL or MariaDB exercises

Install a local MySQL 8.x or MariaDB server and a SQL client such as the
[MySQL command-line client](https://dev.mysql.com/doc/refman/8.0/en/mysql.html)
or [DBeaver](https://dbeaver.io/). Create a scratch database, then review the
relevant exercise notes and run one script at a time.

For example:

```bash
mysql -u <username> -p
```

```sql
CREATE DATABASE sql_practice;
USE sql_practice;
SOURCE /absolute/path/to/course-files-sql-practical-exercises/CreateTable/f67mcxBQkqhz1g9iOGgz_Module_6/Module_6.sql;
```

Some scripts create or select their own database, and several contain
destructive statements such as `DROP TABLE`. Use a disposable practice
database, inspect the script before running it, and adjust database names or
MySQL/MariaDB-specific syntax where necessary. Stored procedures and triggers
use `DELIMITER`; execute them in a client that supports that syntax.

### Formula 1 challenge

The challenge includes a ready-made SQLite database and its SQL source:

```bash
sqlite3 "F1 Challenge/f1_data.db"
```

```sql
SELECT d.GivenName, d.FamilyName, r.position
FROM drivers AS d
JOIN results AS r ON r.driverId = d.driverId
LIMIT 10;
```

The CSV files in [`F1 Challenge/`](F1%20Challenge/) can also be imported into
SQLite, PostgreSQL, or another analytical tool for independent practice.

## Documentation and help

Start with the exercise notes in the directory matching the topic you want to
study. The SQL files contain the course prompts and example solutions. For
database-specific behaviour, consult the official
[MySQL documentation](https://dev.mysql.com/doc/),
[MariaDB documentation](https://mariadb.com/kb/en/documentation/), or
[SQLite documentation](https://www.sqlite.org/docs.html).

If something is unclear or a script does not behave as expected, open a
[GitHub issue](https://github.com/VoidLance/course-files-sql-practical-exercises/issues)
with the database engine/version, script path, command used, and a minimal
error message. Do not include passwords, connection strings, or other secrets.

## Contributing

Contributions from learners are welcome. To propose an improvement:

1. Fork the repository and create a focused branch.
2. Update the relevant exercise notes or SQL resource.
3. Test SQL changes against the documented database engine and explain any
   version-specific behaviour.
4. Keep generated database files, credentials, and unrelated changes out of
   the commit.
5. Open a pull request describing the exercise, change, and verification steps.

Please preserve the educational context and keep examples clear enough for a
learner to follow.

## Maintainer

This repository is maintained by [VoidLance](https://github.com/VoidLance).
Issues and pull requests are the preferred way to ask questions or suggest
improvements.
