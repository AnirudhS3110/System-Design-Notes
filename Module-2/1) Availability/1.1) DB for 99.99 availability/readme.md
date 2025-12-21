# Database Statergy for:
## 99% to 99.9% Availability:
- **Single Primary DB** with **READ REPLICAS**
- **Asynchronous Replication** is fine
- Periodic   backups, but might lose some datas.
- Traditional RDBMS can be used!
- **Simpler Operation Overhead**

## 99.95% to 99.99%
- Multi-Master DB's or Active-active DB's
- Distributed DB's like Cassandra, Dynamo DB , Spanner.
- **Synchronous Replication** so that there is no data loss
- Cross region Replication
- Automatic Fallover with concensus  protocol like RAPHT or PACSOS.
