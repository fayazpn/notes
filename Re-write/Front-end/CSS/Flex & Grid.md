- main axis - vertical -> flex container is column  - horizontal -> flex container is row
- cross axis - horizontal (same like above)
- flex container - parent
- flex item - children
- `box-sizing: border-box` is sizing technique to help with identifying with of elements, this  is the easiest
- use technique below to set box-sizing

```
html {
box-sizing: border-box;
}

*,*::before, *::after {
	box-sizing: inherit;
}
```

- `flex-flow: row wrap` - combined two properties, generally used for responsiveness
-  `align-content:` removes gap between the items
- flex-item props
	- order - used to order the items & re-arrange the columns
	- `flex-basis` - sets the width,  by default the width is content width (diff between width is width is 30%, not flex acc to container width)
	- stretch is used to create equal height boxes, better than playing around with max-height
- `figure` is html markup used to design a unit of items not just image