# Common Mistakes in interviews:
## 1) Not asking about Scale:
## 2) Over engineering for scale you dont need:
- Design Based on requirements, dun Design for 1M+ users for an app with 10K users.
- always strart simple and scale when you need to.
## 3) Under Engineering and Ignoring Future Growth:
- Design the System for atleast 3x to 5x teh Initial Expected Load.
- Otherwise in 6 months if the traffic doubles we need to redesign the entire architecture.

## 4) Ignoring Read/Write ratios:
- Example: You optimise for writes when 95% of the operations is READS or vice versas
- So ALWAYS ASK ABOUT READ/WRITE RATIO.

## 5) Treating All Scale the Same!
- 100M users != 100M reqs/sec != 100TB of data