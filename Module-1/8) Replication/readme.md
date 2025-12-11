# Replication
- Proper replicaion will hel us building High Oerformace SYStem
- System's Performence is often Dependent on its DB, if DB is not available tehn mostly teh System is not available
- Of DB has High Latency Low Throughput, then teh Server will also have high latency Low throughput
- Therfore in order to make High poerfoormant Systems, we need high Performant Database
- Replication is the concept of Having a replica of the Main database, so that if the Main DB goes down there is still Secondary Database, Eliminating Single Point Of Failure.
- Primary DB handles all the Reads and writes coming ot the DB,also updates teh replica, so that all infos are present in the Secondary DB. This thing should be a Synchronous process, that is the primary shd update the Secondary as soo as new info comes
- So, now th esecondary DB can handle if the PRimary DB goes down, and when the Primary DB again comes to action, the secondaru DB updates the PRimary DB with all new infos.
- Replication is also used to Reduce latency induced due to Geographical Locations.
- for example there is DB in US, for a Client in INdia, any updates from the US 