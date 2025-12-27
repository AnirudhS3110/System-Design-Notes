# Consistency:
- Its about whether the user sees the Correct data/ stale data.
- There are 2 types of Consistency:
## 1) Strong Consistency:
- Once a write is complete, Every Server irrespective of the location(It may be in Asia, Europe or US) reads the Same exact data.
- Its like Pretending the Distributed Systems is present as ONe single Data Base, but in reality, its spread across different regions across multiple Databases
- We need it where DATA CONSISTENCY has huge impact, wrong data costs the company loses.
- Used in :
- - 1) **Banking** : Cant add 100 units more
- - 2) **Inventory management(like Ticket Sales)**: One single ticket cant be booked by same person.
- - 3) **Seat reservations/Flight Booking**: one single seat cant be book by 2 different persons.
- - 4) **Authentication**
### Trade-off:
- Its very **Expensive and Slow**.
- **higher latency**: Servers need to Coordinate
- **Lower Availability & Slower Writes**:  We cant write fast because, it needs to be updated to DBs spread among differen t geographical regions.

## 2) Eventual Consistency:
- Choose this if you can compromise little bit of Consistency of Data with Performance.
- After writing has completed in the DB, it wont update the other DBs immediately, rather, it updates all other DBs eventually!
- But in this time interval or window, responses from 2 different servers will be different, i.e users from 2 different regions will see different Response.
- Use case Examples:
- - 1) Social Media Feeds
- - 2) Product Description in Amazon
- - 3) View Counts 
- - 4) Profile updates

### Gain:
- Better performance than in Strong Consistency.
- No waiting around for otehr servers, can handle way more traffic.
- High Availability
- Better Scale.

### Downside:
-  Displaying of Stale Data to the users.
- If 2 users tries to update the same value at the same time(maybe at different regions), we need to figure out methods to solve the conflict.

## <a href="./4.1) Intro To Cap Theorem/readme.md" >Next: Intro to CAP theorem </a>