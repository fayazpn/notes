
Reasons a component can re-render:

- State change triggers a re-render in the **Same component**
- If the parent component re-renders the children of the component re-renders (Which can trigger re-render in the whole component tree)
- When the context state update changes, the value that is using the context will re-render

A component wont re-render if its props changes that is a **Myth**


Props only matter when we use memoization techniques to, then only React will stop and check the children components props changed or not to re-render it.