
2024-08-10 07:50

Status: #child 

Tags: [[frontend]] [[javascript]]

# NextJS Data Handling

- Server components are normal function unlike React components
- We cannot call React components ourselves
- React does it for us, also we cannot bring async behavior in the react component by itself as it should sync return jsx
- We can bring async only through react hooks in react
- But that is not the case for the server components, we can make async calls in the function by itself
- Server components fetch data on the server, as there is no client side js, they do not fall into the render logic, so works like regular js functions
- `fetch` can be used in server components, it has more feature than the normal one such as caching and de-duping features

# References






