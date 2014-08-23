# mysqlctl

Basic set of tools to interact with a MySQL database.

The `mysqlctl` script provides a few easy shortcuts like user/database listing, creation and deletion


## Usage

``` bash
Usage: mysqlctl OPTIONS CMD

OPTIONS: -H, -u, -p, -n, -d, -v, -m, -r
    -H: MySQL host
    -u: MySQL username
    -p: MySQL password
    -n: Dry run. Don't execute any SQL command.
    -d: Debug mode
    -v: Verbose output
    -m: Create database with same name as user
    -r: Delete both user and database

COMMANDS: create|delete|dump|grant|ls
    create [db|user] ITEM
        Create user or database
        -m will create a new database with the same name as the new user
    delete [db|user] ITEM
        Delete user or database
        -r will remove both user and database
    dump DATABASE [TABLE]
        Dump whole database or specific table(s)
    grant DATABASE USER PASSWORD
        Grant access to database to user
    ls [db|user|grant]
        List databases, users, permissions
```
