
2024-06-13 14:25

Status: #child 

Tags: [[python]] [[programming-language]] 

#### Dictionary

It is a data structure which stores key-value pairs, it is ordered means it can be referred by an index
We can store primitive types as key
We cannot make dictionary as key of another dictionary, as it is not hash-able types
We need to convert them to tuple before making them key of the dictionary

##### Normal dictionary  
*Syntax - {}*

*.get(key, default fall back value)* - It is used for getting a value from index 'key' of the dictionary, if not found it will store the *default fall back value*
Using this method we can avoid checking if the key is present in the hash-map or not

#### Default dictionary
*Syntax - defaultdict(type)*

Default dict is used for avoiding case of checking if the element is present in the hash-map or not
It needs a element type such as int, string, list, lambda etc

#### Common Methods
*.items()* - returns array of all the key-value pairs as the tuple 
*.keys()* - returns all the keys of the hash-map
*.values()* - returns all the values of the hash-map
*.pop(key_name)* - removes the given key from the hash-map
*.popitem()* - removes the last item in the array
*.clear()* - clears the dict




# References

https://www.w3schools.com/python/python_dictionaries.asp





