SQL server/instance has four system databases and they must be present to operate affectively.

Master database - 
```
The location of user created database files
Login accounts
server configuration settings
Linked server information
startup stored procedures
```
Model database
```
A template to create new databases
Options set in model will be applied to new databases
The template is used to create tempdb everytime the server starts
```

MSDB database
```
It is critical database and it stores information of various functionalities
Stores historical information of SQL agent jobs, backup and restore history of databases
Metadata information of Jobs, studio, database mail and service broker
```

TEMPDB database
```
Backup and restore not allowed for this databases, data is not permenant
It is recreated everytime the server is restarted
It is shared by all users in SQL server
It is used for temporary objects, online indexes operartions, cursors, table variables and so on.
```

Optional database
```
ReportServer - Available if reporting services are installed
ReportServerTempDB - Available if reporting services are installed
```
Repication system database
```
Available when you configure replication
```

Resource Database
```
Read-only hidden database that contains all the system information
Can't backup the resource database
Must copy paste the file
c:\program Files\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn
```





