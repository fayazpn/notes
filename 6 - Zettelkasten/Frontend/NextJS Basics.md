
2024-08-09 20:07

Status: #child 

Tags: [[frontend]] [[javascript]] [[nextjs]]

# Next JS

##### Static Routing

- `/dashboard/admin`
- Every folder needs to have `page.tsx` for to be render something
-  `(admin)` - route group - used for organizing routes logically without impacting the URL structure

##### Dynamic Routing

- `[id]` - slug based routes
- [...id] - any amount of slugs (`/:id/:title/...`) used when the length of the slug is not known - catch all routes
- `generateStaticParams` - used in combination with dynamic routes, to generate statically at build time
	- Pages are pre-rendered and ready serve


**Special Files**
- `layout.tsx` - for shared layout among the route
- `loading.tsx` - for loading state
- `error.tsx` - for error handling

- to add folder and not to include in the router prefix it with `_`


#### Advanced Routing

**Parallel Routes** - Simultaneously show multiple pages that can be navigated independently, used for split views and dashboards

**Intercepting Routes** - Lets to capture a route and present it within the context of another, maintaining user context across multiple pages


#### Database connection setup

There is way you should setup the database, as DBs are not designed to be in server-less environments, as it cannot handle a large amount of DB connections.
So we should set up in a way that we cache the connection and use the existing one.
There are also pure server-less DB solutions




# References






