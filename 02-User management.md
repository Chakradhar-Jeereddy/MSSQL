-- Query to check all users, groups and logins in SQL server

```
select name login_name, type, type_desc as account_type, is_disabled from sys.server_principals
 where type in ('U','S','G') order by name,type_desc;
```
--Hide all databases to users

```
user master
go
deny view any database to public
go
```
--unhide all databases to public
```
go
grant view any database to public
go
```

Windows domain username/active directory user
```
It is an account that accesses servers within the domain, using windows authentication
Windows groups - Account that accesses a windows domain via a group
```

```
SQL login - Account that accesses SQL server
SQL user - Account that accesses SQL Server database (mapped with sql login)
SQL ROLEs - Set of permissions can be granted to SQL user
```

--create a windows user/sqllogin for SQL server access
```
use master
go
create login DBA\tom --<< Create a SQL login of windows user account to access SQL SERVER ONLY
from windows with default_atabase=master,default_language=us_english
go
```
or
```
use master
go
create login chakra --<< Create a SQL login with sql server authentication to access SQL SERVER ONLY
with password='reddy' must_change,default_database=master,
check_expriation=on,check_policy=on 
go
```
```
Create SQL user using SQL login to access the database
use chakra
create user Tom for login DBA\tom --<sql login
with default schema=dbo
go
```
Grant permissions to sql user to access a table
```
Grant select on HumanResource.Department to Tom as dbo
```
Dropping an SQL login doesn not drop the SQL user. It must be dropped seperately
```
use master
go
drop login DBA\tom --<AD account
go

use chakra
drop use Tom
go
```
Authentication mode for SQL server
```
Windows authentication mode
SQL server and windows authentication mode

Note - If windows authentication mode is used it will disables SQL server authentication mode, by default SA account is disabled.
       If we choose both, it will ask provide strong password for built in system administrator account names sa.
Becuase SA account is well known and often targated by malicious users, do not enable it, instead create another ACCOUNT and grant sysadmin right or rename the SA account.

Verify connection via windows authentication
When use connects through windows user account, sql server validates the account and password using windows protocal token in OS. It has built in security protocal,
password policy, it is recommended over SQL authentication

Verify connection via SQL Authentication
When using SQL auth, login are created in SQL server that is not based on windows user accounts, Both username and password are created by SQL server and stored in SQL server.

Some reason to use SQL Server Authentication
Support older applications
Third party apps require SQL authentication
Supports mixed OS, all users not authenticated by a windows domain
supports web-based apps where users are create there own identiies.
```











