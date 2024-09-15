
2024-08-10 15:34

Status: #child 

Tags: [[frontend]] [[javascript]] [[nextjs]]

# NextJS Middleware


- Middleware is everything that happens before the request
- They are executed even before cached content and routes are matched, their job is to direct the flow of requests based on the incoming data
- It is a function that runs on the edge that protects everything like server-less function, like a traffic stop

```ts
// middleware.ts
import { NextResponse } from 'next/server'
import type { NextRequest } from 'next/server'

export function middleware(request: NextRequest) {
  return NextResponse.redirect(new URL('/home', request.url))
}

export const config = {
  matcher: '/about/:path*',
}
```

We can add *matcher* in config to tell which path the middleware should run on



# References

[[https://scottmoss.notion.site/Middleware-baad1c5575fd4cfca8d167021e9b3922]]




