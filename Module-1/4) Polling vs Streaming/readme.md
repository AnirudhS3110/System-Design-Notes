# Streaming:
- The Server Pushes the Responses to the Client, without any request from the Client
- In Polling th client uses a Set Interval to Request Response from the Server
- For example a server has Information of Weather Temperature.
- As the temperature wld frequently cahnge, teh Client need to Poll the  server every 30s.
- This is not a Suitable method for the Client to Receive the Information
- As this qould create lotss of loadsd onm teh server.
- The client dsoesnt get **Instantaenous** Information when it uses Polling Technique.
- Instead of Polling we should use Straming.
- In streaming, We are gonna have a Long live connection between the Server and the Client, this can be donw with socket.
![alt text](image.png)
- Socket is a file where our System can Write and Read from, and other Systems can  write to the file for communication between the 2 systems.
- Its a open Connectino whihc lives until l one of them chooses to close.
- In Streaming , the CLIENT is LISTENING to the Server not REQUESTING the Server.
- This means, the Server can send message even when the client doesnt ask for any.
- Its the server's job to send info to client whenever the Server wants to.
- Server sending Data to Client ProActivelhy is Called **PUSHING**.
- Streaming is not ALWAYS teh better sln, it depends on the usecase, for example in caht appas , STREAMING is better than Polling<br>
``` GENERAL RULE OF THUMB: IF YOU NEED INSTANTANEOUS EXPERIENCE OR THE SERVER NEEDS TO SEND DATA FREQUENTLY, WE NEED TO USE STREAMING, BUT IF YOU WANT TO UPDATE DATA NOT TOOO FREQUENTLY, LIKE IF YOU CAN UPDATE LIKE EVRY 30s USING POLLING IS BETTER```
