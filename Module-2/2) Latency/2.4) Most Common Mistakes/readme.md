# Common Mistakes
### 1) Talking about Avg latency Instead of Percentile
- Always say p99 latency of specidified seconds, never say avg latency or median latency of 299s

### 2) Ignoring Physics
- We cant promise 50ms latency from US to ASIA, the speed of light to optic fibers is 2lakhs km/s, it's not possible

### 3) Not accounting for Full Request chain:
-  Latencyh compounds across all services in the microservice , should always conmsider total latency caused by each service.

### 4) Forgetting about Cache Misses:
- we can say p99 is 50 ms without cache miss, but it can be 500 ms when cache miss happens, that is it **becomes 10 times slower**

### Over Engineering
- NEVER design  10ms latency for 500 ms latency requirement