## 1)Database Selection
![alt text](image.png)<br>
- For **STRONG CONSISTENCY** : Use PostgresSQL or MySQL with **Synchronous Repilcaton**, MOngoDB is used for majority Write concern!, BAsiucakly Single Leader Replication where writes are synchronous.
- <a href="../../../Terms and meanings/Module-3/SingleLeaderReplication/readme.md"><strong>Single Leader Replication</strong></a>:one node(Leader) is the only one allowed to handle writes, and one or more follower nodes replicate data from it.
- For **Eventual COnsistency**: DBs like DynamoDb and Cassabdra has Tunable COnsistency, which means we can make the DBs either Eventually consistent ot Stringly Consistent based on the needs
- We can use Multi-Leader or Leaderless replication
- Read Replicas with Async Replication

## 2) Caching Statergy:
![alt text](image-1.png)
## Strong Consistency
Use this when reads must always return the latest value.

### Recommended Strategies
- **Write-through cache**
  - Every write in DB should be updated in the cache.
  - Ensures cache is always in sync.
- **Skip cache for writes / read directly after write**
  - Avoids stale data completely.

### Key Behavior
- Immediate invalidation.
- No stale reads tolerated.
- Lower latency benefit compared to eventual strategies.
- Higher write latency (since cache + DB both update).

## Eventual Consistency
Use this when small staleness is acceptable in exchange for speed & availability.

### Recommended Strategies
- **TTL-based cache**
  - Each cached item expires after a set duration (commonly 30–60 seconds).
  - Eventually refreshes to latest value.
- **Cache-aside (Lazy loading)**
  - Read:
    - Check cache → if miss → fetch DB → store in cache.
  - Write:
    - Update DB
    - Invalidate cache or let TTL expire.
- **Optional write-behind**
  - Writes update cache first, database later.

### Key Behavior
- Allows temporary stale reads.
- Better performance & scalability.
- Simpler to manage in distributed systems.
---
## 3) Replication Statergy:
![alt text](image-2.png)