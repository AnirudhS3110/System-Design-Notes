- Consider this case, Millions of video uploads happens simultaneously in Youtube
- If all those Files had to flow through the application servers, then those servers wwould become a massive Bottleneck
- Pre-Signed URLs solve this problem.
### Normal way of uploading video:
![alt text](image.png)
- Uploaded video reaches server, the server Authenticates user, checks informations and forwards teh video to Cloud Storage.
- Now, the Server is handline many GIGA BYTES of data, as thousands of users are uploading Simultaneously the bandwidth of the server gets crushed
- And we are paying all the Data transfer twice, from CLient to server and server to DB.
- Therefore we need a way for users to Directly upload the Video to Cloud, securely without sharing credentials of the cloud and without Bottlenecking our servers. Here comes pre-signed urls 

# Pre-Signed URL:
- It is a Special URL, that GRANTS temporary PERMISSION  to upload or download a specific file, without **NEEDING ANY CREDENTIALS**.
- Then it automatically expires after a set time, which is generally few minutes.