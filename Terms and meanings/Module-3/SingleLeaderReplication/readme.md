# Single leader Replication:
- also called primary–replica or master–slave replication
- database replication model where one node(Leader) is the only one allowed to handle writes, and one or more follower nodes replicate data from it
### Pros:
- Simple conflict model (only one node writes → no write conflicts)
- Easier to reason about correctness
- Good performance for read-heavy workloads
### Cons:
- Single point of failure unless failover configured, but If leader goes down, a follower can be promoted.
- Writes don’t scale horizontally (all writes go to one node)
- Followers may lag → eventual consistency for reads if reading from replicas
- Failover can be tricky and slow if not automated

## When should you use it?
Use it when:
- System is write-light / read-heavy
- You want simple replication
- Strong centralized write consistency is needed

## Avoid if:
- You need multi-region write capability
- Very high write throughput
- Ultra-low failover disruption

## Databases Using Single-Leader Replication

Common databases and platforms that use a single-leader (primary–replica) replication model:

- **PostgreSQL** — Streaming replication
- **MySQL** — Primary–replica replication
- **MongoDB** — Replica sets with one primary
- **Redis** — Primary–replica architecture
- **Cloud Databases**
  - AWS Aurora
  - AWS RDS
  - MongoDB Atlas

  ### <a href="../../../Module-2/4) Consistency/4.2) Impact on Architecture/readme.md"> Return: Impact of Cosistency on Architecture of the system</a>
