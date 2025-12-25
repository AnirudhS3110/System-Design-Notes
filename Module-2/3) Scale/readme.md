# Scale
- In System Design Intervies by FAANG Companies, in order to Design the System, we must Ask 
- - at what scale shd the system be designed?
- - How many users?
- - How manu Requests per Second? 
- This is imp because teh Architecture, DB, Chaching statergy changes for designing for 1000 users and 1M users.

## 4 dimensions of Scale:
### 1) user Scale:
- How many Users does the System needs to Support, in terms of Daily Active Users (DAU).<br>
![alt text](image.png)

### 2) Request Scale:
- how many Request Per second the System needs to Handle?<br>
![alt text](image-1.png)
- A social media app needs 10 thousnds reads per seconf 
- payment system might need 10,000 WRITES per seond
- The ratio of reads and writes also matters enormously!

### 3) Data Scale
- this involves how much data are we storing in terms of GB, TB, PetaBytes
- YT stores 100s of PT of videos<br>
![alt text](image-2.png)

### 4) Growth Rate:
- This involves are we designing for Current Scale or Future Scale<br>
![alt text](image-3.png)
- If there are 1M users rna nd we expect 10M users next year, then we shoudl design in such a way that it accomodates 10M users.

#### NOTE: All these Dimensions Interact with each other
- 1M users making 100 reqs per day is different from 100M users making 1 Request per day. 
- Even the number of requests are same, both are different
- The Architecture needs to be different

## <a href="./3.1) Why Scale is One of the Big 3/readme.md">Next: Why Scale is one of Big 3</a>