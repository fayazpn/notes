
2024-09-23 12:07

Status: #child 

Tags: [[go]] [[programming-language]]

# Go - Context Package

- A Box that carry information for every request
	- Trace ID
	- Cancellation timeout
	- User info
- Can get the user details in the user service using the *get context "userId"*
- It is an immutable tree, to mutate it, we need to create a new context
- The timeout added to the context, when requesting to another micro-service from a micro-service, if it exceeds the timeout, we can cancel the request all to together, also if any other additional requests are made, that can also be cancelled. (User does not hang here)


# References






