### Replication

#### Intro
- MongoDB provides two flavors of replication: *master-slave replication* and *replica sets*. For both, a single primary node receives all writes, and then all secondary nodes read and apply those writes to themselves asynchronously.
- Master-slave replication and replica sets use the same replication mechanism, but replica sets additionally ensure automated failover: if the primary node goes offline for any reason, then one of the secondary nodes will automatically be promoted to primary, if possible [MongoDB in Action]()
- Changed in version 3.0.0: A replica set can have up to 50 members but only 7 voting members. [1] In previous versions, replica sets can have up to 12 members. 

#### Replica Set Members
- **Primary**. The primary receives all write operations.
- **Secondaries**. The secondaries replicate the primary’s oplog and apply the operations to their data sets such that the secondaries’ data sets reflect the primary’s data set. You can configure a secondary to: Priority 0 Replica Set Members, Hidden Replica Set Members, Delayed Replica Set Members.
- **Arbiter**. An arbiter does not have a copy of data set and cannot become a primary. Replica sets may have arbiters to add a vote in elections for primary. Arbiters always have exactly 1 election vote, and thus allow replica sets to have an uneven number of voting members without the overhead of an additional member that replicates data.


### Sharding
