# Latency:
- Its the time the System Takes to Respond to the Request,usually measured in MilliSeconds.

# What Causes Internet Latency:
- principal causes of network latency is the distance between client devices making requests and the servers responding to those requests
- If the Distance between the server and the client is 100miles then the latency is 5-10 ms
- if the distance is 2,200 miles, then the latency is about 40-50 ms (This is jus teh time taken by the data to travel btw the Server and the client)
- Data traversing the Internet usually has to cross not just one, but multiple networks. The more networks that an HTTP response needs to pass through, the more opportunities there are for delays

## Round Trip Time:
- The amount of time it takes for a response to reach a client device after a client request is known as round trip time (RTT).
- RTT is equal to double the amount of latency, since data has to travel in both directions — there and back again.

# Percentile Latency:
## P50 Latency (Median):
- This means 50% of teh Request is faster the other 50 is slower
## P95 latency:
- 95% of the requests are faster than this
## P99 Latency:
- 99% of the Requests are faster than this

# Average Latency:
- Assume a System's Avg Latency is 100ms
![alt text](image.png)
#### Average LAtencies hides these problems, Percentile Latency shows these!

## Percentile Latency Benchmarks for Different Systems:
![alt text](image-1.png)

# Human pereption of Latency:
![alt text](image-2.png)

## Interview POV:
- Its always better to ask about the Latency Requirement, either P95 or P99 

### <a href="./2.1) Why Latency matters/readme.md">Next Section</a>
