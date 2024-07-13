
2024-07-12 10:56

Status: #child 

Tags: [[programming-language]] [[go]]

# Go Fundamentals - Intro

- Go has features such as being memory safe and channel based concurrency
- Go once written and compiled, it is packaged into a single standalone executable file, it is self contained. It does not require you to install anything additional. 
- Once written we can compile it down to the OS of our choice.
- Go is statically typed and has type safe memory model with garbage collector that automates memory management
- Go is designed to take advantage of multiple CPU cores

`package main`
- All go code should start with this
- If you want to run the code directly, then name it *main*
- Else name it something else and import into another code base
- All the go files in the same directory are considered part of the same package. So it must all have the same package name

- Go has module system, to  use one just import it using an import path
- It will be downloaded in the next time
- import only apply to the file they are declared in, so we need to do same imports again, but can be managed by other tools

`var helloList = []string {}` - global variable declaration

**List Types**
There are 3 types in Go for list, in which all are key-value pairs collections
- Array - contiguous and users numbers are key, first element is 0
- **Slices** - contiguous and uses numbers are the key, first element is 0
- **Map** - We get to choose the type of key in this data-structure, we use this when we need some data to look up value in the map

**Functions** -
`main` - special function in go, where this is called the entry point of the application. There can only be one main function within a *main* package, when go runs, the main function is called automatically.

**Struct** - are collections of properties and function, like objects in other languages




# References
[[Go Fundamentals - Variables]]
[[Go Fundamentals - Operators]]
[[Go Fundamentals - Value versus pointer]]





