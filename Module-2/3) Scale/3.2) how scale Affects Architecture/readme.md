# How Scale Affects the Architecture of the System:
## 1) Determines the Database Statergy:
#### Small Scale:
- Lets say 10K users
- Single MySQL DB is enough
- We can design 1K requests per second
- Simple Architecture
#### Medium Scale:
- 100k to 1M users
- NEED READ REPLICAS to distribute read Traffic
- PRIMARY DB handles Writes
- Can use Redis / Memcache for Caching
#### Large Scale
- 10M+ users
- SINGLE DB cant handle the whole Volume of requests.
- NEED to **Shard the Data across multiple DBs**
- or Switch to NOSQL DISTRIBUTED DBs like Cassandra/Dynamo DB, whicih are designed for Horizontal Scaling
- Both approach has Tradeoff
##### - Sharding is comlex but gives you complete control
##### - NOSQL scale easily but lacks the SQL features we want

## 2) Caching
#### Smale Scale:
- No caching needed as DB is fast enough
#### Medium Scale:
- use Redis/memcached, use cache-aside pattern to cache most frequently asked data
#### Large Scale:
- Aggressive Caching needs to be done,because every DB query we AVOID saves MONEY and IMPROVES LATENCY
- Aim to achievew 95 to 99% cahce hit rate, as you shd avoid making calls to DB
- Caching at multiple-levels
- using CDNs to cache Static Contents
- Applicaton level caching of User Sessions
- Redis Clusters to cache HOT data.

## <a href="../3.1) Why Scale is One of the Big 3/readme.md">Previous: Why Scale is One of Big 3</a>
