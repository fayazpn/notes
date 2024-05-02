- Component becomes readable and re-usable
- Main reason for re-render is state change or parent re-render

****
**Moving State down**
- If a state is just used by a single elements and it is used in a component with a lot of heavy child elements,
- we should move the state down to a separate component along with all the elements that use the state
![[Moving state down.jpg]]

****
**Passing components as children prop**
- If a heavy component is passed as a children props of the parent component,
- and the parent component re-renders, the component passed as the ```<ParentComponent>
	  <HeavyComponent />
  </ParentComponent>
  - This is same as passing component through a prop called *children*
  - And a component does not re-render (HeavyComponent) when the parent re-renders as its passed as the props
  - Do not confuse this as with putting it as direct children
****

