
2024-06-25 13:19

Status: #adult

Tags: [[backend]] [[aws]]

# AWS Types of Pre-signed URLS

**Types of URLS**

GET - we can use this pre-signed URL to download specific object from s3 bucket, without needing AWS credentials
 You can generate a pre-signed URL using
 ```bash
aws s3 presign s3://finance-department-bucket/2022/tax-certificate.pdf
```

The result of running is

```bash
https://s3.amazonaws.com/finance-department-bucket/2022/tax-certificate.pdf?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIA3SGQVQG7FGA6KKA6%2F20221104%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20221104T140227Z&X-Amz-Expires=3600&X-Amz-SignedHeaders=host&X-Amz-Signature=b228dbec8c1008c80c162e1210e4503dceead1e4d4751b4d9787314fd6da4d55
```


This URL works even though the bucket is not public. That is basic idea of the pre-signed URL where the content is private by default and expose them in a limited controlled way when necessary

- **https://s3.amazonaws.com – The base URL for S3 APIs.
- /**finance-department-bucket** – The name of the bucket.
- **/2022/tax-certificate.pdf** – The key of the object.
- ?**X-Amz-Algorithm=AWS4-HMAC-SHA256** – The signature algorithm being used.
- &**X-Amz-Credential=AKIA3SGQXQG7XXXYKKA6%2F20221104%2Fus-east-1%2Fs3%2Faws4_request** – The credentials being used for this pre-signed URL. Note that this string contains the Access Key ID (**AKIA3SGQXQG7XXXYKKA6**), the region (**us-east-1**), the service (**s3**), and the type of request (**aws4_request**). Also, note that the related secret access key is not disclosed (that one remains known only to AWS).
- &**X-Amz-Date=20221104T140227Z** – The timestamp when the signed URL was generated.
- &**X-Amz-Expires=3600** – The offset (in seconds) when this pre-signed URL will expire. This is 1 hour by default, but it can be customized.
- &**X-Amz-SignedHeaders=host** – The list of HTTP headers that will be used to calculate the signature (by default only the **host** header).
- &**X-Amz-Signature=b228dbec8c1008c80c162e1210e4503dceead1e4d4751b4d9787314fd6da4d55** – The actual signature of the request.

When a user makes a GET request to this URL, AWS will verify a few things:

- That the URL is not expired
- The credentials used to generate the URL are not expired
- The content of the request matches the signature provided in the URL.

The *signature* check is important as for instance if user tries manipulate key, such as change the object to download, AWS can immediately that this is the request that was authorized when the URL was generated and block the OP

Pre-signed URLS cannot be invalidated once they are used, they are only invalidated once the expiry hits.

***

**PUT** - Pre-signed URLs that can be used to authenticate uploads to S3. 

In the PUT request we have *Content-length* header which specifies the size of the request body. As it contains the raw bytes of the upload.

Just like **GET** requests, the PUT Pre-signed URL will contain all the necessary info needed for the AWS to validate before uploading

Limitations 
- Cannot set limit of upload size (max 5GB)
- Cannot give a generic content type, need to be specific of the content type
***

**POST** - If the considerations such as a user should be able to upload more than 5GB, then we should use POST a.k.a Form Pre-signed URL

They use *multiform/form-data* encoding which is used to serialize the content of web-forms that might contain file attachments

So in here we are actually dealing with *pre-signed* form than Pre-signed url, we need to generate pre-signed form with different fields

It is more flexible than PUT as it uses policy mechanism, it allows the signer to define 'rules' that can control what can be uploaded. 
- Specify the range of supported file sizes
- Specify multiple contents
**Quirks of POST**
- If we need to submit form through JS (AJAX), we need to enable CORS on the bucket
- Can only upload one file at a time.
- File must be the last in the field, other field after will be ignored


# References

[[https://fourtheorem.com/the-illustrated-guide-to-s3-pre-signed-urls/]]




