
2024-08-10 12:34

Status: #child 

Tags: [[javascript]] [[nextjs]] [[frontend]]

# NextJS Server Actions

- Running code on server from the client side, calling function that gets executed on the server
- We do not need to setup a new API route
- If used in client component
	- in the form submit function, use `use server` directive on the top and pass that function to the `action` of the form element
	- create `utils` file and use `use server` directive on the top and create server actions as normal utils function
- Problem is, we cannot have response from the server actions, makes it create for side effects
- For to get response, call from the client
- to access the formData the standard is `formData.get('<fieldName>')`
- With server actions we cannot by default tap into doing optimistic update because of lack of API response, to achieve it we need to write some client side code
- Else we can revalidate the page that is getting data using `revalidatePath` function inside the server action - but this gives a flickering effect as the whole ui is getting render
- So, the cache is deleted for the page and fetched again
- For form validations we need client component, So just take the part which needs validation and make it client component rather than making the whole thing client
- Server actions is not everything, there are use cases
- If there are no forms, we need to setup to run server actions a different way, so in that case it is better we do it client side itself
- Example: to mark a to do as completed, we can use `useTransition` to run the server action `onClick` of a *client component*

# References






