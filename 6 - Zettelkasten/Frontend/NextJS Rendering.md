
2024-08-09 23:16

Status:  #child 

Tags: [[frontend]] [[javascript]]

# NextJS Rendering

#### Rendering
- Static routes render the components at the build time and cache the result
- Dynamic routes render the components on the server at the request time
- By default NextJS statically renders the route and caches the result of the `fetch` requests that did not opt out from the caching behaviour, if revalidated the route will re-render statically during re-validation
- During static rendering, if a dynamic function or a `fetch` dynamic, NextJS will auto switch to dynamically rendering the whole route at request time. Any cached data request can still be re-used during dynamic rendering
- Dynamic routes rely on info that is known at request time like user cookies, current request headers,
- Using search params `cookies()` or `headers()` in server components will opt the whole route into dynamic rendering at request time
- For dynamic data fetches are `fetch` with *no-store* or *revalidate* to 0
- You cannot import a *server component* directly into a *client component*, you can pass the *server component* as a children prop to the *client component* and render it that way
- We can import client component to a server component




# References






