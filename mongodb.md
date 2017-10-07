### Replication
- MongoDB provides two flavors of replication: *master-slave replication* and *replica sets*. For both, a single primary node receives all writes, and then all secondary nodes read and apply those writes to themselves asynchronously.
- Master-slave replication and replica sets use the same replication mechanism, but replica sets additionally ensure automated failover: if the primary node goes offline for any reason, then one of the secondary nodes will automatically be promoted to primary, if possible
- The only time you should opt for MongoDB’s master-slave replication is when you’d require more than 11 slave nodes, since a replica set can have no more than 12 members. [MongoDB in Action]()


### Sharding
