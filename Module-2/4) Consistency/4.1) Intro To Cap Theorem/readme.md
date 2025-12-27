# Cap Theorem
## Network Partition:
-  Consider 2 Servers one in New York another in London
- If the medium  of Communication between the 2 servers cuts, for example Router Failure, Cable Cut, Data Center Outage
- It results in Isolation of the 2 servers
- Both teh servers will be running and functioning as usual, but they cant communicate.
- This is called Network Partition.
- **Paritions are Inevitable**
- At this time we need to either choose between CONSISTENCY or AVAILABILITY.

## Cap Theorem:
- At time of **NETWORK PARTITION** which one to choose for the system: **CONSISTENCY** or **AVAILABILITY**
### Consistency Priority(CP systems):
- They choose Consistency over Availability.
- At time of network partition, they reject some requests so that they dont show any Stale Data.
- **Its better to be temporarily unaivalable than to show Wrong Data**
- We use this in Banking, Inventory, Authentication, **anything where inconsistent data causes loses/harm**
- **Example: MongoDB, HBase, etcd**
### Availability Priority(AP Systems):
- Used where Availabilty matters over Data Consistency instantly.
- These return Responses even at the time of Network Partition, but they may return STALE DATA.
- **Example: Cassandra, DynamoDB, Riak**
### Tips to articulate the answers on CAP theorem:
![alt text](image.png)

## <a href="../readme.md">Prev: Intro</a>
## <a href="../4.2) Impact on Architecture/readme.md">Next: Impact on Architecture</a>