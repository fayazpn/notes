
2024-08-09 23:18

Status: #child 

Tags: [[javascript]] [[frontend]]

# NextJS Layout and Templates

### Layouts

- Layouts are components that are shared between pages, used for common elements like navigation elements
- They are only rendered once
- They do not render on route changes
- Created with creating `layout.js`
- There should be a root layout in the app
- Can create many root layouts when using *route grouping*
- Any route can have layout, making it nest-able
- Layouts can fetch data, but cannot pass the prop down to its children

### Templates

- Templates are the exact same as Layouts, except the do render every time a route changes.
- Useful for enter and exit animations and useEffect logic that happens on render
# References






