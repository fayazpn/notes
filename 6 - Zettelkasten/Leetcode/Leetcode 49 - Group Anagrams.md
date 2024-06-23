
2024-06-11 15:36

Level: #medium

Tags: [[ds algo]] [[arrays & hashing]]

#  Arrays & Hashing

**Approach 1**  - Slower
- Init  *defaultdict(list)*
- Loop through each array elements
	- init {}
	- loop though each letter
		- create hash-map of letter count
	- index the mapped letter hash-map as key and append the looping string to the value 
- return hash-map.values()
```python
class Solution(object):

	def groupAnagrams(self, strs):
	
		"""
		
		:type strs: List[str]
		
		:rtype: List[List[str]]
		
		"""
		
		hashmap = defaultdict(list)
		
		for string in strs:
			h = {}
			for s in string:
				if s in h:
					h[s] += 1
				else:
					h[s] = 1
			
			hashmap[tuple(sorted(h.items()))].append(string)
		
		return hashmap.values()
```

**Key Takeaways**
 - defaultdict - solves the problem of checking if key exists or not and initializes a default value according to the type of the dictionary
 - dict cannot store non hash-able type, hence convert the *h* to tuple
 - sort it, or else duplications happens
 - *h.items()* returns array of tuples, as key-value pair
 - *h.values()* returns values of the hash-map as array

***
**Approach 2**
- initialize *defaultdict* hash-map
- create an array of 26 letters with 0 as each elements
- loop through every element in the array
	- loop through every character of the string
		- find the index number of the string in *array26*, subtract the ascii value of a from the current character in loop
		- increment it by 1
	- convert the array to tuple and keep it as key and append to that the current string
- return *hashmap.values()*
```python
class Solution(object):
	def groupAnagrams(self, strs):
		"""
		
		:type strs: List[str]
		
		:rtype: List[List[str]]
		
		"""
		
		hashmap = defaultdict(list)
		
		for string in strs:
			arr = [0] * 26
			for char in string:
				index = ord(char) - ord('a')
				arr[index] += 1
			hashmap[tuple(arr)].append(string)
			
		return hashmap.values()
```

**Time Complexity - *O(nk)***
**Space Complexity - *O(nk)***


# References

Youtube video link - https://www.youtube.com/watch?v=vzdNOK2oB2E&ab_channel=NeetCode




