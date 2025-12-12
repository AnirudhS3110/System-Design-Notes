# Single Point Of Failure(Important Concept, simple to Understand, Critical to master):
- It's any component, which can bring down the ENTIRE System when it FAILS
- Examples:  server crash, Database Failure.
- Goal in System Design is to Identify those Single Point of Failures and Elimate it before its too late.    
- **NOTE**: DataBase is the Most important SPOF in any System.
- Lets consider a basic Cloud Architecture:
![alt text](image.png)
#### Function of API Gateway:
- Every Request first hits APi gateway.
- it Checks from whom the request came
- Figures out where teh request should go
- Then sends it to the right place