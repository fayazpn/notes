
2024-06-25 12:01

Status: #child 

Tags: [[backend]] [[aws]]

# AWS S3

AWS Simple Storage Service is an object store service which offers scalability, availability of data, pre-signed URLs among other features.

By default it is private, we need AWS CLI or AWS SDK to programmatically access the bucket. Which requires a policy that allows credentials to perform these actions.

We can define IAM policies to give permission to the application so that it can read and write to the s3 in a controlled way

In the news letter example, we cannot let a random person with the link to access the document. We need to create a 'specially crafted' URL that gives the receiver temporary access to the resource.


# References

https://fourtheorem.com/the-illustrated-guide-to-s3-pre-signed-urls/




