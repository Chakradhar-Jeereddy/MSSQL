When a new database is created two files gets created by default
```
a) data file with .mdf extension, it holds data
b) transaction log file with .ldf extension, it records transactions

Transaction log file - It sequentially records all changes to the database.
                       Data is writen in tran log before it is commited to datafile.
                       A checkpoint event is triggered on tran log file to indicate that data is witten from buffer to the datafile.
                       This process flushes committed transactions and maintain size of physical transaction logfile (only in simple recovery mode). 
                       Purpose of transaction log backup is to perform point in time recovery and transaction log itself is for instance recovery in case of crash.
```
Auto growth and sizing of transaction log
```
What happens when autogrowth is expanding?

It cause performance issues, it blocks the operations untill auto resize event is completed.
More the autogrowth event, higher the fragmentation of transaction log. 
Auto growth should be used for safety reasons only.

Pre-size data and log files (manually manage data and log files) to reduce fragmentation issues.
```
Understanding datafile/transaction log file -> ATM example
```
To withdraw 100$ from blance 500$, many events are recorded in transaction log and only results are stored in data file.
If you intiate another transaction, the previous information in transaction log is inactive tansaction and new transaction is writen to the log file.
At some point we need to remove inactive transactions from the log file, to maintain its size. If not, it will halt the database.
```

