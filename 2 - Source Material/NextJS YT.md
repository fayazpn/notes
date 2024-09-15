

### T3

- mini code review with `git add -p`
- stage all `git add -A` - includes the new file
- Ignore ts error and eslint error in next config to have faster build step and move those to the github actions
- add `--turbo` flag to the *dev* script
- choose ts version specific to the project by selecting it
- force dynamic the page, as it is static by default it gets cached
- `_components` - inside the app folder


**Authentication**
- create middleware file in the src directory and paste the clerk setup code
- `SignedOut` - clerk component which renders stuff to show when not logged in
- `SignedIn` - ..
- Can do this in every place where we need to switch contents based on the authentication
- import `auth` from `/nextjs/auth` for more performant import

**Routing**
- curl from terminal


**Data fetching**
- If updating the client component for the latest data then use `const router = useRouter(), router.refresh()`
- this re-executes all data fetches on the current page


**Tainting**
- Instead of accessing the db directly from the component, which can lead to issues like security and consistency
- Good pattern is the db access in separate file in `server` folder
- `use server` - exposes endpoint for the client to hit
- `import "server only"` - work only on the server 
- Tainting is blocking certain parts of data like token or password from going to the client side (read the docs)


**Image component**
- setup the `hostname` for optimization only from domain of your choice
- height, width, style with objectfit contain

**Sentry**





### File Drive


**To-do**
- Github
- Convex
- Clerk
	- JWT convex


- When using clerk signin with modal, allow user session





### General
- how to route to dashboard from clerk login
- how to integrate state management

