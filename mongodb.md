### Replication

#### Intro
- MongoDB provides two flavors of replication: *master-slave replication* and *replica sets*. For both, a single primary node receives all writes, and then all secondary nodes read and apply those writes to themselves asynchronously.
- Master-slave replication and replica sets use the same replication mechanism, but replica sets additionally ensure automated failover: if the primary node goes offline for any reason, then one of the secondary nodes will automatically be promoted to primary, if possible [MongoDB in Action]()
- Changed in version 3.0.0: A replica set can have up to 50 members but only 7 voting members. [1] In previous versions, replica sets can have up to 12 members. 

#### Replica Set Members
- **Primary**. The primary receives all write operations.
- **Secondaries**. The secondaries replicate the primary’s oplog and apply the operations to their data sets such that the secondaries’ data sets reflect the primary’s data set. You can configure a secondary to: Priority 0 Replica Set Members, Hidden Replica Set Members, Delayed Replica Set Members.
- **Arbiter**. An arbiter does not have a copy of data set and cannot become a primary. Replica sets may have arbiters to add a vote in elections for primary. Arbiters always have exactly 1 election vote, and thus allow replica sets to have an uneven number of voting members without the overhead of an additional member that replicates data.

#### Replica Set Deployment 
- **Deploy an Odd Number of Members**.
- **Consider Fault Tolerance**. Fault tolerance for a replica set is the number of members that can become unavailable and still leave enough members in the set to elect a primary.
- **Use Hidden and Delayed Members**. To support dedicated functions, such as backup or reporting.
- **Load Balance on Read-Heavy Deployments**. In a deployment with very high read traffic, you can improve read throughput by distributing reads to secondary members. 
- **Distribute Members Geographically**

#### Replica Set Elections
Factors and Conditions that Affect Elections:
- Heartbeats
- Member Priority
- Loss of a Data Center
- Network Partition

### Sharding
#### Sharding Components
- **shard** - contains a subset of the sharded data. Each shard can be deployed as a replica set.
- **mongos** - acts as a query router, providing an interface between client applications and the sharded cluster.
- **config servers** - store metadata and configuration settings for the cluster (deployed as a replica set).
#### Sharding Strategy
- **Hashed Sharding** involves computing a hash of the shard key field’s value
- **Ranged sharding** involves dividing data into ranges based on the shard key values.
