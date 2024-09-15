
2024-09-07 19:52

Status: #child 

Tags: [[typescript]]

# TS - Objects, Arrays & Tuples
- *Optional Property* - is signified by *?* in the property
- **typeof** - used in js and ts to check the type of a variables
- **Type Guard** -  checking the type of the variable before using it
- **Type Narrowing** - checking the type of the variable and reducing the possible set of values that a variable can be
- TS will object when we are defining an object literal type and not use it, it is called *excess property checking*
- **Index signatures** - `{[k:string]: string}` -  when using a known property use a dot notation for accessing the property or use bracket notation
- **Array** - `Array<string>` - less preferred & `string[]` 
- **Tuples** - made from *Array* in ts, if we have a set positioning for data in the array elements where we know what data is in the certain position then we can make it a couple
	- Here we can cast the array, so to prevent the said array being able to be populated we can do *type annotation*, downside being we can access methods of js array like *push* & *pop* but the length will be the original literal type
	- **readonly** - treats it as an immutable array and array properties does not exist anymore
- **Structural vs nominal**
	- nominal typing is lang like Java where the instance of the object is checked if belongs to a certain constructor
	- structural type is what ts is where it checks the shape of an object rather than where it is created from, it checks if it contains the properties that is needed (duck typing), even if the object contains more properties than what the function needs, func still accepts (set of allowed values modal) - which makes it accepts args of diff constructors
	- *instanceof* - is a way of making ts acting like nominal type system

# References
https://frontendmasters.com/courses/typescript-v4/objects-property-types/





