- A system's performance is often Dependent on its DB
- To Build High Performance Systems, we need Huigh Performance Databses.

## Replication Lag:
![alt text](image.png)
- Its the Time period where the Replica is not updated with the new Data which is written in the Primary DB.
- Replications helps with READ Scalability and AVAILABILITY, but doesnot HELP with WRITE SCALABILTIY
- IF teh System is WRITE HEACVY, HAving Replicas aloner wont solve the problem, This is where we use Sharding

## Trade-Offs of hacing Strong Consistency and Eventual COnsistency:
- Synchronous Writing enables to enables to maintain Data Consistency, but the WRITES are SLOW.
- Asynchronous Writes enables High availability, Faster Writes when compared to Synchronous writing, but not 100% Consistent, this system tend to data loss when the PRimary DB goes down.  
## DBs which support Replication:
![alt text](image-1.png)

## Why choose Replicas:
- High Read Availability
- Fault Tolerance
- Scale Read Operations
## limitations:
![alt text](image-2.png)