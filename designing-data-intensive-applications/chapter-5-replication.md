# Replication

Replications means having multiple copies of the same data in multiple nodes that are connected. Replication is done for the following reasons -
- reduce latency by keeping data closer to clients.
- increase availability by serving data even when some nodes are down.
- increase read throughput by handling multiple requests across the nodes.
- allow applications to continue working even during a network disruption

### Three replication algorithms
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
    - Choose a new leader. The follower with the most up-to-date data becomes the new leader.
    - Reconfigure the system to use the new leader. 
- *Downside*: Clients can't write to the database if it cannot connect to the leader or if the leader is down for some reason.

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


## Multi leader Replication

- Allow more than one node to accept writes. That node should forward that data change to all the other nodes.
- Applicable for Multi data centers, with a leader in each data center.
- Applicable for clients(such as mobile phones) with offline operations, where the local database also becomes one of the leaders.
- Applicable for real time collaborative editing such as Google Docs.
- *Downside*: Same data may be concurrently modified in two different datacenters, and those write conflicts must be resolved.

### Handling Write Conflicts

- Write conflicts are the biggest problems in Multi leader replication
- Requests from a particular can be sent to the same leader all the time
- *Convergent conflict resolution*: All replicas must arrive at the same state after all changes are replicated
- Conflict resolution is transferred to the application and triggered on reads or on writes.
- A *replication topology* describes the paths in which the writes are replicated from one node to another:
    - Circular - one leader forwards writes to one other node
    - Star - writes are replicated to one designated root node.
    - All to all - Every leaders sends writes to every leader

## Leaderless Replication

- This kind of database is also known as *Dynamo-style*.
- Provides high availability and low latency, but can have occasional staleness.
- Two common approaches -
    - clients send writes to several replicas
    - clients send writes to a coordinator node
- Read requests are also sent to several nodes in parallel and the data with the latest timestamp or version is accepted.
- **Read repair**<br>
When a client knows it has received a stale value from one of the replicas, it writes the newer value to that replica.
- **Anti-entropy process**<br>
A background process copies data from one replica to another replica in case of any differences.

### Quorum
- When there are *n* replicas, every write must be confirmed by *w* replicas and we should query at least *r* replicas for each read to get an up-to-date value, then *w + r > n*.
- Read and write requests are sent to *n* replicas in parallel, the numbers *w* and *r* determine how many nodes we wait for.
- Quorums can return stale values in the following cases -
    - *Sloppy quorums*: write to available replicas, even if the designated replicas are not reachable. 
    - Concurrents writes or concurrent reads + writes.
- *Hinted handoff*: The sync between replicas once the replicas are reachable after a sloppy quorum is fixed. This provides high availability in sloppy quorums.
- Applicable to multi datacenter replications, where a quorum is ensured within the local data center.

### Detecting concurrent writes**<br>
- *Last write wins(LWW)* - Each replica will store only the recent most value
- *Happens-before relationship* between writes
- *Concurrent operations* - Operations which do not know of other conflicting operations are called concurrent, even if they occur at different physical times.
- *Merge concurrent writes* - Merge concurrently written values
- *Version vectors* - Version number is maintained per replica per key. Version numbers collected from all other replicas is called a Version vector and is used to detemine which values need to be over written.












