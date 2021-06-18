# ACID
All of operations will be success or fail. Either execure or not at all.

Consistency : Leaving the system in a consistent state. For: ex we send money from one account to another
if transaction succeded then the total sum of the balance in the accounts should be same.

Isolation: Transaction should be executed in isolation from other transaction. One transaction updates a value, will the other transaction see that change? There are
multiple isolation levels.
<br>
Isolation levels define the degree to which a transaction must be isolated from the data modifications made by any other transaction in the database system

Durability: The changes in the db should persist. Persistence in the case of failures 

## Reads in Db
Dirty Read
> A Dirty read is the situation when a transaction reads a data that has not yet been committed. For example, Let’s say transaction 1 updates a row and leaves it uncommitted, meanwhile, Transaction 2 reads the updated row. If transaction 1 rolls back the change, transaction 2 will have read data that is considered never to have existed.

Non Repeatable read
> Non Repeatable read occurs when a transaction reads same row twice, and get a different value each time. For example, suppose transaction T1 reads data. Due to concurrency, another transaction T2 updates the same data and commit, Now if transaction T1 rereads the same data, it will retrieve a different value.

Phantom Read
> Phantom Read occurs when two same queries are executed, but the rows retrieved by the two, are different. For example, suppose transaction T1 retrieves a set of rows that satisfy some search criteria. Now, Transaction T2 generates some new rows that match the search criteria for transaction T1. If transaction T1 re-executes the statement that reads the rows, it gets a different set of rows this time.

## Isolation Levels
Level | Dirty Read | Non Repeatable Read | Phantom Read
---| --- | --- | --- |
Read Uncommitted | Possible | Possible | Possible |
Read Committed | Solved | Possible | Possible |
Repeatable Read | Solved | Solved | Possible |
Serializable | Solved | Solved | Solved |

Read committed is the default transaction level in Postgre, repeatable read in MySQL.

# Transactions in Java
Two types of annotation exist Spring provided and Jpa provided.
Jpa provided(javax.annotation) can work on single db operations.
If you want to provide a transaction guarantee across multiple db or mq, you need Spring provided.
<br>
We can also use isolation levels in spring annotation.

# View vs Materialized View
View | M-View
--- | --- |
Doesnt physically hold data | Holds data physically | 283 |
No mechanism to refresh | Fast/Complete options | 283 |
Less performance | better performance