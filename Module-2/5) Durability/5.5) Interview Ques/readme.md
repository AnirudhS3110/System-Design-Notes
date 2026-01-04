# Design a banking System
- Durability Requirements for Transactions in banking System
    - For Financial Transcation we need Maximum Durability
    - So we use PostgresSQL DB with SYNCHRONOUS Replication atleast across 3 availability Zones.
    - We should commit every transaction to the WAL and before sending the success essage, the WAL needs to be Flushed into the Disk through FSYNC.
    - 7 Years **Point in Time Recovery**
    - TradeOdd: 10-15 ms to the existing latency, but its better to take time instead of ending up losing data and trust amongg the customers.

# Design an Realitme Analytics Dashboard.
- Durability requirement of Analytics Dashboard can be loose:
    - In analytics Dashboard, most of the values are result of a Computation, so loss of Data of few seconds doesnt mattewr as it can be recomputed.
    - Redis with fsync EVRY SECOND for HOT data.
    - in memory aggregates.
    - Async Persist to Data Warehouse like SnowFlake, no ned to be synchronous. 
    - Benifits: sub- millisecond latency.

## <a href="../5.4) CheckPointing/readme.md">Prev: CheckPointing</a>
## <a href="../5.6) Understanding TradeOffs/readme.md">Next: UNderstanding Trade-Offs</a>