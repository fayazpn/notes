# DNS and network protocols

Map: [[Maps/Systems|Systems]]

## Summary

DNS resolves names into records such as addresses. IP provides packet delivery; transport protocols add different delivery and communication behavior.

## Key points

- An A record maps a name to an IPv4 address; an AAAA record maps it to IPv6. A CNAME points to another name.
- A registrar manages domain registration. Authoritative nameservers serve the domain's DNS records; recursive resolvers find and cache answers.
- TCP gives applications an ordered byte stream with retransmission and flow/congestion control. A failed connection can still leave uncertainty about a remote action.
- UDP sends datagrams without a built-in delivery or ordering guarantee. Applications may add their own reliability.
- ICMP carries network control and diagnostic messages. `dig`, `ping`, and `traceroute` answer different diagnostic questions.

## Related

- [[Notes/Systems/HTTP HTTPS and transport|HTTP HTTPS and transport]]
- [[Notes/Systems/Server provisioning|Server provisioning]]
