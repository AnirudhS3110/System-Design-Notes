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

## 3) Load balancing:
#### Small Scale:
- Single Server is enough, NO load balancing is needed
#### Medium Scale:
- Multiple Servers behind single Load balancer is sufficient
#### Large Scale:
- In large scale, Servers will be present in Different Geographic locations, therefore GLSB(geographic Server Load balancers) is needed
- That is Load balancers in asia will distribute the traffic among servers in Asia, same in Europe, there will be mulrtiple levels of Load balancing
- The architecture will also be Microservices, because different services may need different scaling

## 4) Data Storage:
#### Small Scale:
- Files on same server

#### Medium Scale:
- S3 object storage

#### Large Scale:
- uses CDNs to deliver content globally
- we choose different levels of Storage Tiers
- hot storage for frequently accessed contents
- Cold Storage for archived contents
- Might also have own CDN infrasturcture as the volume is High

## Anychronous Processing and Queues:
#### Small Scale:
- most of the things Synchronously
#### Medium Scale:
- Message Queues for heavy Operations
#### Large Scale:
- mandatory async processing
- use Kafka/SQS to handle millions of messages per second
- Have worker pools which handles jobs in parallel
- When the queue gets tooo long, it causes BACK PRESSURE, the entire architecture becomes event driven

## NOTE:
### At Smale Scale Vertical Scaling is Fine
- Systems which scale only vertia=cally will hit a linmit, and that limit costs too high
### At Large scale, teh system needs for Horizontal Scaling.

## <a href="../3.1) Why Scale is One of the Big 3/readme.md">Previous: Why Scale is One of Big 3</a>
## <a href="../3.3) common mistakes/readme.md">Next: Common Mistakes</a>
