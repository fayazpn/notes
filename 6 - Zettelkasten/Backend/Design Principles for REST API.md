
2024-09-23 13:56

Status: #child 

Tags: [[backend]]

# Design Principles for REST API
- Standardized, Stateless & Cacheable
- All API requests should look the same
- `GET /v1/users/feed`
	- `GET` - HTTP METHOD
	- `uses` - *resources* should be plural
	- `feed` - action/resource

REST is not related to HTTP,  but uses it to power the web apps
Server does not store any client context between requests, all the request must contain the necessary information needed to process the request


**CRUD**

C reate -> POST (PUT)
R ead -> GET
U pdate -> PATCH/PUT
D elete  -> DELETE


**Statelessness**
- The info about the user is derived from the token or something similar
- Server does not store any client context between requests, all the request must contain the necessary information needed to process the request




# References

https://ics.uci.edu/~fielding/pubs/dissertation/fielding_dissertation.pdf





