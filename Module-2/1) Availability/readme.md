# Availability:
![alt text](image-4.png)
- Availability id the percentage of time that our system is Operational and Available to the USer.
- Expressed as 'uptime-99%', uptime 99.99%
- We cant achieve 100% availabiulity, Achieving Higher Availanility makes the system more complex ands teh cost exponentiaklly raises
- Every System wiull have downtimes or breaks duw e to Network Partition, Hardware Break, Data centers go down.
- It's one of the Big 3 concepts.
![alt text](image.png)


## Three Pilllars of MEasuring Availability:
### Service Level Indicator:
- Its the actual measurement in terms of %.
- Example: Requestr rate: 99.5%, System Responds 99.9% of time

### Service Level Objective:
- This is the Target measurement or metric we are trying to achieve whle designing the System.
- Its internal Target, that is promise made to stakeholder
- this is "What are we Aiming for?"
- THese are stricter than SLA's
- Examples: miantain 99.95% availability, 99% of API requirements within 100ms.

### Service Level Agreement(SLA):
- This is the promise metric / measurement made tot he customer, often with Financia Penalties.
- Its like "What are we legally commited to?"
- Example: "we guarantee 99.9% uptime or you get 10% credit", "If availability is lss than 99%, then custiomers get 25% refund", "API abvailabiltiy 99.95% or compensaion."
- These Contract based, if the cmpanies or devs break them, they need to do as per the Contract

## Note:
- 99.9% availability gives 43 mins downtime per month
- 99.99% Availability gives 4 mins downtime per month

## 99.9% Availability:
-  We will set up Active-passive Databse set up that is, 1 primary and 1 secondary DB.
- Single region Deployment with Backup
- basic Health Check Ups.
- Load balancers in single Availability Zone.
- Lower Infrastructure Cost

## for 99.99% Availability:
- **Active Active MUlti-Region Deployment**
- Multiple Replicas Across Availability Zones.
- No Single Point of Failure
- Automatic Fallover with minimal Dataloss
- Chaos Engineering for testing.

## Higher Availability means **Multi-Region Deployment** !
- this is because if one Availability Zone completely fails, all the traffic to this will be Directed to other Healthy AZ's.
- Will survive entire Data Center Failures.
- But this will lead to **Cross Region Latency and Data Consitency Challenges!**

## THe Heirarchy:- SLI must be Greater than SLO, and SLO must be greater then SLA.
![alt text](image-1.png)

## Error Budgets:
- If SLO of your company is 99.9%, then Error budget is 0.1%, which provides your company 43 minutes per month for downtime or deployment

## Interview POV:
- You are asked to design a payment
- Your approach should be, First you should ask what is th Error Budget for this. For example lets assuem lets keep error budget as 99.99% or higher as AVAILABILITY then it would give us approximately 22 minutes per month as error budget
- Let's commit to the customers as 99.9% SLA
![alt text](image-2.png)
![alt text](image-3.png)
