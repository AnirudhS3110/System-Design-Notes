# Why scale is one of the big3:
## 1) It Determines if the Design Works
- The system designed for 10k users will completely break for 1M users.
- Its fundamentally wrong to keep singel Postgres DB for a system which needs to handle 1M writew per second, the DB will be a Bottle neck from DAY-1

## 2) It shows that you understand  Cost & Efficiency:
- In small scales Inefficiency doesnt matter much
- In Large scale, every Inefficiency Multiplies!
- If a Server makes 10 DB reqs for 1 reqs it fine with Small Scale, but it's detremental if the Scale is Large, costs explode and becomes un-managable.

## 3) It shows that you think about the entire System Life-Cycle:
- We are not just Designing system for current number of users, we are designing for Expected number of Users
- Design for 10x to 100x growth from day 1, otherwise need to rebuild everything later.

### So, when we ask the question of what is the scale to the interviewer, it means all this!

## <a href="../readme.md">Previous: Intro</a>
## <a href="../3.2) how scale Affects Architecture/readme.md">Next: Impact of Scale on Architecure</a>