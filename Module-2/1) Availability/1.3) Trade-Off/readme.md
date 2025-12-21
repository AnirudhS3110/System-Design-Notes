# Trade-offs and Mistakes:
## Cost Vs Availability:
- Going from 99.9% to 99.99% Availability doubles or Triples your Infrastructure Costs as:
- Having Replicas in Multiple Regions and Multiple Availability Zones.
- need to use Sophistiocated Monitoring Systems.
- More DB replicas
- More Operational Overheads
- Longer on-call teams

### Moving to 99.99% increases the cost by 2 or 3 times that of 99.9% Therefore this decision should be taken based on Impact of Downtime over the Business.

## Consistency and Avaiability(Cap Theorem Trade Off):
- Higher Availability means **Accepting to Offer Eventual Consistency**.
- 

## Mistakes:
![alt text](image.png)
![alt text](image-1.png)
#### Availability is only as good as the Weakest Link in the Dependency Chain:
![alt text](image-2.png)
- The service might be Highly Available, but what about these things which you depend on:
- - DB
- - Cache
- - Message Queue
- - Third Party APIs
- We also need to Discuss Availability of our Dependencies.
- **Example: If we call Payment Gateway, what is their SLA? or do we need Circuit BReakers?
![alt text](image-3.png)
