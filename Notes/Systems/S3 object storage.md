# S3 object storage

Map: [[Maps/Systems|Systems]]

## Summary

Amazon S3 stores objects addressed by bucket and object key. Application access is controlled by permissions and related bucket settings.

## Key points

- Use narrowly scoped application permissions for the objects and operations required.
- Keep object bytes separate from relational metadata when that fits the workload; a database can store the object key and ownership information.
- A CDN can cache selected content near readers; cost and cache behavior depend on the deployment.
- A presigned URL provides temporary access to a specified operation without handing the caller the signer's credentials.

## Related

- [[Notes/Systems/S3 presigned URLs|S3 presigned URLs]]
