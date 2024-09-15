
2024-08-10 06:30

Status: #child 

Tags: [[frontend]] [[javascript]]
 
# NextJS Navigation

#### < Link > Component
- Extends the anchor tag
- Provides pre-fetching capabilities
- Primary and recommended way for routing
- can use `usePathName` to check the active links
- By default scroll behaviour is top and maintains the scroll for forward and backward navigation
- To scroll to id do the convention of `/dashboard#thing`
- Disable scroll restoration with `scroll={false}`


#### `useRouter()` Hook
- Allows to change routes programmatically in client components
- `router.push('/dashboard')` on click

#### `redirect` function
- in Server Components we use this function instead
- returns 307 (Temp redirect) by default
- In server actions returns 303 (redirect on success of a POST request)
- `redirect` throws error, so wrap in try catch
- Can be called in client components render process, but not in event handlers, we use `useRouter` instead
- Accepts absolute URLS, so can give external routes
- If redirect before render use `next.config.js` or `Middleware`

#### Native History API
- `window.history.pushState` and `window.history.replaceState` lets to update history without reloading the page
- pushState is used to update the URL without reloading the page while pushing a new entry into the history 
	- sorting
	- filter
	- step in multistep form
- replaceState is used to update the URL without page reload without creating a new entry
	- search query param
	- saving form progress
	- replace login page history with home page


#### Routing and Navigation
- Hybrid approach for navigation and routing
- In server the code is auto code-split by route segments
- in client, prefetched and cached the routes so it doesn't reload the page
- **Code Splitting** - In server component, it is split by route basis, and only that code is loaded in navigation
- **Prefetching** - can be done using `< Link >` and `router.prefetch()` for pre-fetching programmatically 




# References






