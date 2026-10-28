# Hashing encryption and signatures

Map: [[Maps/Systems|Systems]]

## Summary

Hashing, encryption, and digital signatures solve different problems; they are not interchangeable descriptions of secure communication.

## Key points

- A hash maps input to a digest. It does not provide a decryption operation.
- Encryption protects confidentiality and is reversed with the appropriate key.
- A digital signature lets a verifier check a message against a public key; it does not conceal the message.
- Password storage needs a suitable password-hashing design, not a plain fast hash. A checksum alone does not authenticate a downloaded file against a malicious publisher.
- SSH authentication and its encrypted transport involve several mechanisms; “the private key encrypts everything” is not an adequate model.

## Related

- [[Notes/Systems/HTTP HTTPS and transport|HTTP HTTPS and transport]]
- [[Notes/Systems/Server provisioning|Server provisioning]]
