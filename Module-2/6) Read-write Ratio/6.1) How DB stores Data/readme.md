## B-tree vs LSM Tree
- Th echoice of B tree or LSM tree changes the Shape of the System's performance.
- If the System is Read heavy: Choose B-Tree based DB, which is SQL DBs. Example: MySQL, PostgreSQL
- If the System is Write Heavy: Choose LSM Tree based DB , which is NoSQL DBs . Example: Cassandra, Dynamo DB
![alt text](image.png)