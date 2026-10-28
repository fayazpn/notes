# S3 presigned URLs

Map: [[Maps/Systems|Systems]]

## Summary

A presigned URL authorizes a specific S3 operation for a limited time using the signer's permissions.

## Key points

- The backend authenticates the requester, chooses an object key and operation, and generates a signed request. The client transfers the bytes directly to S3.
- GET commonly downloads an object; PUT uploads to a selected key. A presigned POST uses a form and policy conditions for supported upload constraints.
- Anyone possessing the URL can use its granted capability. It is not automatically single-use, and an upload to an existing key can replace that object.
- Expiration can be shortened by credential expiration or permission changes. Do not log or share signed URLs unnecessarily.
- Large-object upload is a separate multipart-upload design decision; POST is not a general workaround for upload size limits.

## Related

- [[Notes/Systems/S3 object storage|S3 object storage]]

## Sources

- [AWS S3 presigned URLs](https://docs.aws.amazon.com/AmazonS3/latest/userguide/using-presigned-url.html)
