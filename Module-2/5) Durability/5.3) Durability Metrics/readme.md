# Durability Metrics:
## Recovery Point Objective(RPO):
- RPO Directly Determines the Durability Statergy used in the System.
- This answers the Question, how far your system can **Tolerate Data Loss**.
- If the System Crashes at this moment, from how many minutes or Hour back of data do you intend to Roll Back.
- Whether you willing to loss the data in the Previous Minute, or Previous Second or Previous Hour, or do you need Zero Data Loss it depends on the system you are building.
- If RPO is 5 mins, then your system can Afford data loss of 5 minutes, this is acceptable in Social Media App. Async Replication is fine
- The RPO must be 0 for payment System, THis implies **SYNCHRIONOUS REPLICATION**
- RPO with 1 hr, Async Replication with Hourly Sanpshot is fine.

## Recovery Time Objective(RTO):

- How fast should you shd recover data, based on the Cost of System Downtime.
![alt text](image.png)
- It drives our Availability Set Up.


## Cost of Resucing the RPO and RTO of the System:
- Going from 1 hr RPO to 0 RPO will Increase the cost Exponentially more(atleast 10x), in terms of Infrastructure.
- It would also add Significant amount of Latency to every write.

## <a href="../5.2) Durability mechanisms/readme.md">Prev: Durability Mechanisms</a>
## <a href="../5.4) CheckPointing/readme.md">Next: CheckPointing</a>