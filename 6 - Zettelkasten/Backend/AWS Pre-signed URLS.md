
2024-06-25 11:41

Status: #adult 

Tags: [[backend]] [[aws]]

# AWS Pre-signed URLS

Server-less architecture is when, we are not in charge of managing the infrastructure

Use cases for pre-signed URLS

- Avatar upload from user
- Game binary upload from user to play store, and download by player
- Document upload to cloud
- Marketing campaign, users fill up for newsletter will get a link to download a white-paper. The link should be secure and have expiry
- Inter-system comm workflow where components need to exchange large files. we don't put a large payload in the message, instead we attach a document URL which the receiving system will use to download.

USER -> Server -> S3

Upload flow 
- User comms to server that they intend to upload a file
- Server authorizes the user and uses server credentials to generate s3 pre-signed URL for uploading an object with predetermined name into the s3 bucket
- User receive the pre-signed url and uploads.

Download Flow
- User requests the server to download a certain file
- Server checks if its okay for User to download it
- Server uses its own credentials to generate pre-signed URL to GET the certain file.
- User receive the download URL

**Security Considerations**

Server does not talks to S3 directly
URL is validated by AWS at req time (when user makes HTTP call with the URL). AWS will consider this request as if it was performed by the entity that generates pre-signed URL. So if our server is not auth to perform actions to the bucket, user will see a permission error.
# References
[[AWS S3]]
https://fourtheorem.com/the-illustrated-guide-to-s3-pre-signed-urls/
[[AWS Types of Pre-signed URLS]]





