
2024-07-13 16:33

Status: #child 

Tags: [[programming-language]] [[go]]

# Go Fundamentals - Scope

- All variables live in a scope
- Top-level scope is package scope
- Parent-child rel is defined when the code compiles not at the run-time
- When accessing the variable, go looks at the scope where it was defined in
- If it cannot find the in the current scope, it looks above the scope chain
- If a variable is mentioned, it looks up the scope until it can find the variable defenition
- If a variable is found but if it is of the wrong type, Go raises an error
- While **Shadowing** a variable, we can change the type of the variable
- Go's static scope resolution does not care where the function is called
- We cannot access the variable in child scope



# References






