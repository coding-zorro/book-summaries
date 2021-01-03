# Transactions

Transactions is a way to group several reads and writes together into one logical unit. Either the entire transaction succeeds(*commit*) or it fails(*abort*, *rollback*).

**Atomicity**<br>
Multiple writes are grouped together in one transaction. It can also be defined as the ability to abort the transaction on error and discard all writes which are part of that transaction.

**Consistency**<br>
Consistency is when some properties(invariants) about the data is always true. These invariants are defined by the application usually.Unlike others, Consistency is a property of the application.

**Isolation**<br>
Concurrently executing transactions are isolated from each other and do not affect each other. When the transactions are committed, the result is same as if they were executed serially.

**Durability**<br>
Once a transaction is committed, the data which is written is never lost.


