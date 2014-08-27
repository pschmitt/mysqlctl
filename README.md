# mysqlctl

Basic set of tools to interact with a MySQL database.

The `mysqlctl` script provides a few easy shortcuts like user/database/table
listing, creation and deletion.


## Usage

```
Usage: mysqlctl OPTIONS CMD

OPTIONS: -H, -u, -p, -n, -d, -v, -m, -r, -b, -z
    -H: MySQL host
    -u: MySQL username
    -p: MySQL password
    -n: Dry run. Don't execute any SQL command.
    -d: Debug mode
    -v: Verbose output
    -m: Create database with same name as user
    -r: Delete both user and database
    -b: Set backup directory
    -z: Compress backup

COMMANDS: create|delete|backup|dump|truncate|grant|ls
    create [db|user|table] ITEM
        Create user or database
        NOTE: To create a table you have to specify the database:
            $ mysqlctl create table DATABASE TABLE # or: DATABASE.TABLE
        -m: Create a new database with the same name as the new user
    delete [db|user|table] ITEM
        Delete user, database or table
        NOTE: To delete a table you have to specify the database:
            $ mysqlctl delete table DATABASE TABLE # or: DATABASE.TABLE
        -r: Remove both user and database
    backup DATABASE [TABLE]
        Backup database or specific table
        -z: Compress backup (gzip)
        -b DIR: Set backup directory (default is PWD)
    dump DATABASE [TABLE]
        Dump whole database or specific table(s)
    truncate DATABASE TABLE
        Truncate a table
        NOTE: To truncate a table you have to specify the database:
            $ mysqlctl truncate DATABASE TABLE # or: DATABASE.TABLE
    grant DATABASE USER PASSWORD
        Grant access to database to user
    ls [db|user|grant|tables]
        List databases, users, permissions, tables
    sql [DATABASE] SQL_QUERY
        Execute arbitrary SQL command on DATABASE
        NOTE: When database is omitted none will be selected
```
