# CSS layout and styling

Map: [[Maps/Web development|Web development]]

## Summary

Flexbox arranges items primarily along one axis; Grid describes rows and columns. The box model determines how sizes include padding and borders.

## Key points

- A flex container's `flex-direction` defines the main axis; the cross axis is perpendicular to it.
- `justify-content` works along the main axis; `align-items` aligns items on the cross axis. `align-content` distributes flex lines when applicable.
- `flex-basis` is the starting main size before free-space distribution; it is not always simply a width.
- `box-sizing: border-box` includes padding and borders in declared width/height.
- In Next.js, global CSS and `.module.css` files serve different scoping needs. Check the styling tool's version before copying its configuration.

## Example

```css
*, *::before, *::after { box-sizing: border-box; }
.row { display: flex; gap: 1rem; flex-wrap: wrap; }
```

## Related

- [[Notes/Web/Web performance|Web performance]]
