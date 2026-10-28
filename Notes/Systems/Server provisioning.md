# Server provisioning

Map: [[Maps/Systems|Systems]]

## Summary

A provisioning checklist should establish reliable access, permissions, process management, and recovery before exposing an application.

## Key points

1. Choose the operating system and supported runtime versions; apply the required updates.
2. Configure a non-root administrative user and SSH key access. Verify a separate login before changing existing access.
3. Restrict inbound ports to the required services. Preserve the access route needed for administration.
4. Run the application with appropriate permissions and a process supervisor.
5. Configure the reverse proxy, DNS, and TLS for the actual hostnames.
6. Verify logs, monitoring, backups, and a recovery path.

Disabling remote root login is different from deleting the root account. Distribution-specific commands and paths must be checked before use.

## Related

- [[Notes/Systems/NGINX reverse proxy|NGINX reverse proxy]]
- [[Notes/Systems/Linux command reference|Linux command reference]]
- [[Notes/Systems/DNS and network protocols|DNS and network protocols]]
