
2024-09-21 14:35

Status: #child 

Tags: [[programming-language]] [[typescript]]

# Interfaces and Type Aliases

**Type Aliases**
- named type definition
- will completely disappear from the code base
- Will hold any types unlike the *intersection*
- We can build type alias using other *type alias* with *intersection type* sort of like *inheritance* inn OOP


**Interfaces**
- should be object-ish
- `extends` is one of two keyword which mimics the *inheritance behaviour* in types
- We can extend interfaces to build other interfaces
- `implements` keyword is used to define a contract that a class must adhere to, it is used to type the class in some ways, can only be used in class, they work sometimes with type aliases
	- the problem with type aliases is that, it can be non object type, so stick with *interfaces*


**Open Interfaces** - we can make additional interface declaration with same name, it gets squashed together into 1 single interface, and it will be reflected everywhere
- use case is when working with external library and needs to add new method by ourself


**Recursive Types** - `type NestedNumbers = number | NestedNumbers[]`

```ts
type JSONPrimitives = string | number | boolean | null

type JSONObject = { [key:string] : JSONValue }

type JSONArray = JSONValue[]

type JSONValue = JSONPrimitives | JSONObject | JSONArray
```




# References






