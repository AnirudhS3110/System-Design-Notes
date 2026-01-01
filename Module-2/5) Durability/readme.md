# What is Durability?
- When the System says the data is **saved** , the data will persist in the system irrespective of any Failure. This is Called Durability.
- Its not just about Saving the data, it sbaout to what level of Catastrophe the data can Survive.

## Three Different levels of Durability:
- Weak(Fast)
- Moderate(balanced)
- Strong(Expensive)

### Note: Stronger the Durability Gurarantee the more it costs in **Performance** , **Complexity** and **Money**

# Different Levels of Durability:
## 1) In-Memory Only (**No** Durability):
- Data lives only in RAM
- One sytem restart results in lose of all data.
- Used to store Session Information, Rate Limitting COunters, Real time analytics which can be Recomputed
- **Advantage** : Results retrieved approx 1 MICROSeconds latencies.
- **DownSide** : Zero Durability
- Example: Redis , Memcahced


## 2) Single Disk persistance (**Weak** Durability):
- Data is Written to disk which is present only in One server, i.e **no replicated DB**
- If process crashes we can recover
- But if disk Fails or Server Dies, there is a problem
- Latency is approximately 5 milli seconds
- SQLite, Single PostgresSQL

## 3) Sync Replication (**Strong** Replication):
- This is what most Production use.
- Write is not Completed untill all DBs in the Distributed DB acknowledges that data has been stored.
- This causes huge latency: about 10 to 20 milliseconds per ride
- But there is no chance of Data loss (100% Durability)
- It Survives Server and Disk Failure, as DB replicas are done synchronously.
- example: PostgresSQL using synchronous Replication , Mongo DB with majority write consent.

## 4) Async Replication (MOderate Replication):
- Success is returned just after Data is only written in Primarry DB, and eventually is written to other Replicas
- Risk: If main DB dies before Replicas get the Data, then  loss of data will occur.
- But gives better Performance than Sync Replication
- MySQL with async replicas, PostgresSQl with Async replicas.

## 5) Multi Region Replication (**STRIONGEST**):
- Survives Regional Disasters, as Data is stored in Different Regions.    
- Data is **Synchronously** Replicated over Multiple Geographical Regions.
- Example: Google Spanner, Cockroach DB, High durability Configurations of Dynamo DB does it.
- Latency : 50-200ms of latency
