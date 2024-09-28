Simple, full, bulk logged
Recovery model determines how the transaction log size needs to managed and the possibily of transaction log backup and point in time recovery.
```
Simple recovery model - In this mode transaction log backup is not supported.
                        Automatic logfile truncation at every checkpoint gets enabled and releases space to the system by shrinking the log file.
                        Point in time recovery is not possible, possibility of data loss is high.
                        Transaction log backup is not allowed.
```
```
Full recovery model  - Supports transaction log backup.
                       The log will not get truncated at every checkpoint.
                       Transaction log backup will copy the commited transactions from log file to backup file.
                       It will allow to overwrite/reuse the unused space in the logfile. 
                       Transaction log backup marks unused space available for overwriting.
                       Chances of data loss is low, it actually depends on the frequency of transaction log backups.
```
Bulck logged recovery model - It support transaction log backup.
                              The mode is used for bulk DML operations.
                              The log will not get truncated at every checkpoint.
```
```
Demo 

use master
go
alter database test set recovery full;
go
alter database test set recovery simple;
```
