
2024-07-08 11:10

Status: #child 

Tags: [[backend]]

# HTTP - HTTPS - HTTP2

- Made with 2 distinct part *Request* & *Response*
- Will have path *GET ..*
- Host name *Host: fayazpn.dev*
- Rest are headers - info on more details
	- User-agent: Requesting device type
	- Accept: What device will handle
	- Accept-language - Browser Langugaes
	- Content-type - the type of media
	- Set-cookie - set stateful information
	- X- - used for custom header
- Cookies
- Status Codes
	- 1xx -  Information
	- 2xx - success
	- 3xx - redirect
	- 4xx - client error
	- 5xx - server error

### HTTPS

- Unlike in **HTTP** where nothing is encrypted, a man in the middle can sniff out what is being sent between the client and server
- HTTPS on the other hand, encrypts the messages using the keys which are present with the client and server
- We cannot do HTTPS over just an IP address, we need a domain name


### CertBOT
Gives free SSL certificate to 

### HTTP2

- HTTP 1.1 is single req-res cycle
- HTTP2 can do multiple req-res in one cycle


### IP
- Program sends message with *header* and *body*
- Unreliable about the delivery and about the order in which transmitted 
### TCP
- Reliable delivery
- Ordered delivery - received packets are ordered upon receiving 
- Two way channel between the client and server, identified with IP address and ports
- 3 steps process to establish the connection
- HTTP is build on top TCP/IP



# References






