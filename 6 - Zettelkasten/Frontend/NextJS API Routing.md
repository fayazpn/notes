
2024-08-10 15:03

Status: #child 

Tags: [[frontend]] [[javascript]] [[nextjs]]

# NextJS API Routing

- we can start writing service by creating `api` folder
- create `route.ts` file and export functions with appropriate HTTP verb
```ts
export const GET = async (request: Request) => {...
		return NextResponse.json({message: 'Hello'})
	}
```

the `Request` parameter is from the fetch object type
- `NextResponse` is a wrapper of MDN `Response` object

This is like lambda functions, where the functions are in a server-less env, when a route is hit, the function is read into the memory, executed and shut down for the most part unless some techniques are applied
Its scalable, and best used for horizontal scaling


to get the data from a *POST* request 
```ts
data = request.json()
```


#### CORS
- Security policy that browser implements that stops the websites accessing info that are not in the same domain
- So the browser does a *pre-flight* check and checks the *options* of the server to see if origin belongs to the allowed list of domains and method
- Only browser makes the CORS



# References






