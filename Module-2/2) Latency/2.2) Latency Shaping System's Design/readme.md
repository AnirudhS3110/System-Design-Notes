## 1) Geographic Distribution
- The light travels at 2 lakh km/s in optic fibers, its the limitting speed, cant go speeder than it.
- Here we give time taken to one Round trip travel between different regions:
![alt text](image.png)
- The Highest is 120ms, so if interview says to design a system with **p99 < 100ms as GLobal latency**, then it needs:
- - Multi- Region Deployment
- - CDN for Static Content
- - Latency Based Routing to send Clients or users to the Nearest Server.
- If they say p99 < 500ms is fine then:
- - Single region Deployment
- - Use CDN only for Static Assets
- - Standard Load Balancing


