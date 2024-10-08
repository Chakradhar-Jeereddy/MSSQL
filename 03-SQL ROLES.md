What are SQL roles?
```
Predefined collection of objects and permissions
Roles allow DBA to manage permissions more efficently
```

a) We first create roles
b) assign permissions to role and 
c) add logins to the roles

Four types of SQL sever roles
```
1) Fixed database roles (pre defined permissions)
2) Fixed server roles (,,,,,,)
3) Use defined database roles - These roles have set of permissions defined by system admin
4) user defined server roles -  ,, ,, ,, ,, ,,
```
Database level roles
```
a) db_owner - Member of db_owner fixed database role can perform all config and maintenance activties and also drop database.
b) db_securityadmin - Member of thi role can modify role membership and manage permissions(be careful)
c) db_accessadmin - Can add or remove database access for windows,sql server logins and windows group logins
d) db_backupoperator - Account with this role can perform database backup
e) db_ddladmin - Allows to run DDLs in database
f) db_datawriter - To perform delete, update, insert into tables
g) db_reader - Access and read data from all user tables
h) db_denywriter, db_denyreader
```
Server - Databases - Security - Roles - database role - new database role - name(access) - owner(dbo), (select default role), add role member(db user)
Securables - what objects you wish to add, specify objects, all objects of the type, all objects of schema
permissions - grant access


SQL server roles
```
bulkadmin - fixed server role can run the bulk insert statements
dbcreator - Member of dbcreator fixed server role can create, alter, drop and restore any database
diskadmin - to manage disk files
processadmin - to terminate processing running in instance
public - All users, groups, roles by default belong to public role
securityadmin - member of securityadmin fixed server role manage logins and their properties.
               They can grant, deny and revoke server-level permissions and database level permissions, 
               also reset login passwords.
serveradmin - restart server and change serverwide configuration options
setupadmin - Add and remove linked servers and can execute system stored procedures.
sysadmin - Super user can do anything and everything.
```

Permissions
```
GRANT - Allows principal to perform an action
DENY - It will supersedes other collective permissions, denies permission to a login(principal)
REVOKE  - Deny or remove permissions to the securable
```



