# Replication

Replications means having multiple copies of the same data in multiple nodes that are connected. Replication is done for the following reasons -
- reduce latency by keeping data closer to clients.
- increase availability by serving data even when some nodes are down.
- increase read throughput by handling multiple requests across the nodes.

### Three popular replication algorithms
- Single leader
- Multi Leader
- Leaderless

## Single leader replication
### Terminologies -
- *Replica*: Node which stores a copy of the database
- *Leader*: Replica which accepts write requests from clients and writes new data to its local storage first.
- *Follower*: All other replicas are followers and accept the data change from the leader through a change log.
- *Replication lag*: the delay between a write happening on the leader and being reflected on a follower

### Types of replication -
- *Synchronous*: The leader waits until all followers confirm that they received the writes before reporting success to the client.
- *Asynchronous*: The leader does not wait for a confirmation from the followers after it sends the writes to them.
- *Semi Synchronous*: There is one leader and one synchronous follower and the other followers are asynchronous.
Asynchronous replication is used more widely.

### Other considerations -
- Setting up new followers: Backups of the leader database is copied over to the new follower. The follower retrieves the data changes after the backup and applies them on it's local database.
- Handling node outage(Follower): The follower maintains a log of data changes it has received from the leader. After the follower recovers, it can connect with the leader and request for all data changes after its outage and apply them on its local database.
- Handling node outage(Leader): A *failover* has to happen when the leader has an outage. The following are the failover steps:
    - Determine the leader has failed
    - Choose a new leader. The follower with the most upto date data becomes the new leader.
    - Reconfigure the system to use the new leader. 

### Replication Methods
- *Statement based replication*<br>
The leader logs every write request (statement) that it executes and sends that statement log to its followers.

- *Write ahead log(WAL) shipping*<br>
The leader sends it WAL to its followers which uses them to build an exact copy locally.
This is used in PostgreSQL and Oracle.

- *Row based replication*<br>
A logical log is a sequence of records describing writes to a database table. The logical log is replicated to the followers.

- *Trigger based replication*<br>
Triggers are used to write change logs which can then be replicated to other followers.


### Consistency models
- *Read-after-write consistency*<br>
Users should always see data that they submitted themselves.

- *Monotonic reads*<br>
After users have seen the data at one point in time, they shouldn’t later see the data from some earlier point in time.

- *Consistent prefix reads*<br>
Users should see the data in a state that makes causal sense: for example, seeing a question and its reply in the correct order.


## Multi leader replication

- Allow more than one node to accept writes. That node should forward that data change to all the other nodes.
- Multi data centers, with a leader in each data center.
- Applicable for clients(such as mobile phones) with offline operations, where the local database also becomes one of the leaders.
- Applicable for real time collaborative editing such as Google Docs.
- *Downside*: Same data may be concurrently modified in two different datacenters, and those write conflicts must be resolved.









