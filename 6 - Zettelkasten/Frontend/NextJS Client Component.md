
2024-08-10 11:55

Status: #child 

Tags: [[frontend]] [[nextjs]] [[javascript]]

# NextJS Client Component

- we need to opt into the component with `'use client'` to make it a client component
- Even if it is a client component it is still server side rendered as in we need to check if it is server env or browser env for adding features
- In this case first initial components are rendered, sent to the client as html, then javascript is sent, which is then replaced, SSR
- Cannot use services like accessing DB, Redis as this is not executed on the server like the *Server Components*, rather just rendered
- We can use *Client Components* in the *Server Components* and vice-versa, caveat is that we cannot pass *non serializable* props between them (Event handlers etc)
- This is because we cannot serialize functions, it should be serialized to pass through the network barrier

# References






