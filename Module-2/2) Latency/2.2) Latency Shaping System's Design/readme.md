## 1) Geographic Distribution
- The light travels at 2 lakh km/s in optic fibers, its the limitting speed, cant go speeder than it.
- Here we give time taken to one Round trip travel between different regions:
![alt text](image.png)
- The Highest is 120ms, so if interview says to design a system with **p99 < 100ms as GLobal latency**, then it needs:
- - Multi- Region Deployment
- - **CDN for **Static** Content**
- - Latency Based Routing to send Clients or users to the Nearest Server.
- If they say p99 < 500ms is fine then:
- - Single region Deployment
- - Use CDN only for Static Assets
- - Standard Load Balancing

## 2) Caching Statergy:
- **Understanding Latency Heirarchy is crucial**:
- **RAM Access -  100 ns**
- **SSD Read - 100 micro seconds**
- **Network Call within the Same Data center - 1 to 5 milli seconds**
- **Database Query - 10-50 ms**
- **Cross- Region call - 50 to 200 ms**

- Redis Uses RAM to store data whereas normal DBs stores SSD or HDD to store data, therefore Retreiving from Redis isFaster than in normal DBs, about 1000 times faster.
- Redis is In Memory DataBase which Stores the Data in Computer's RAM, so when the Ca=omputer turns off, all the Datas is lost.
- Application LEvel caching doesnt mean Client-Side Browser CAche, it means Caching in Backend System, like through Redis. or Server Cache. Browser caching is limitted only to the user's browser, but server side cache or eedis cache can help with access of multiple users.

### For systems with P99 < 100ms:
- Use Redis/MemCached for storing Frequentky accessed data inmstead of hitting the Main DB.
- IMplement Application level Caching.
- CDN Edge Caching
- Cache HIt rate should be nearly high over 95% 

### For Systems with P99 < 500ms:
- We can implement much less Aggressive Caching
- Can allow more cache misses
- Use Simpler Invalidation statergies

## 3) Database Selection:
### For P99 < 50ms:
- Should use only in-memory DBs like Redis or memcached as it uses RAM as database storage
- SHould never use Disks  I/O in Hot path

### For P99 < 200ms:
- use Fast NOSQL Dbs
- READ replicas Closer to the User.
- Excellent Indexing

### For P99 < 1s:
- Use Traditional DBs like PostgresSQL ,  MySQL
- Can use COmplex Queries


# 4) Synchronous VS Asynchronous Processing:
- This is Huge for Latency. Imagine Designing Twitter:
![alt text](image-1.png)

### For  systems with P99 < 200ms
- Use Async Processing For HEavy Operations.
- need Message Queues like Kafka or SQS
- Return FAST. do processing later

# 5) Service Communication:
- Every time when we call from one MicroService to another, it causes Latency
- Each Data center hops causes 1-5ms, along with Serialization  and Authentication Checks as Overheads.
- Example:<br>
![alt text](image-2.png)
### for P99 < 100ms:
- Minimize Service Hops between the MicroServices.
- Use gRPC instead of REST protocol as gRPC is faster than REST.
- If there is possibility of parallelizing making calls, do it as much as possible rather than calling Sequentially.

### <a href="../2.1) Why Latency matters/readme.md">Previous Section</a>
