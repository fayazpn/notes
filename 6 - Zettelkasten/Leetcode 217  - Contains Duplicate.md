
2024-06-10 01:22

Level: #easy

Tags: [[ds algo]] [[arrays & hashing]]

# Arrays & Hashing

####  Using set()

```python
class Solution(object):
	def containsDuplicate(self, num):
		"""
		
		:type nums: List[int]
		
		:rtype: bool
		
		"""
		seen = set()
		for i in num:
			if i in seen:
				return True
				
			seen.add(i)
			
		return False
```


**set** is collection of elements which are *un-ordered*, *unchangeable* and *un-indexable* and does not allow duplicated

###### Time Complexity - *O(N)*
- All operations except the loop is O(n) complexity, set(), add() is O(1) as its implemented by hash-tables
###### Space Complexity - *O(N)*
- set can grow n times in worst case scenario


# References

Youtube Video Solution - https://www.youtube.com/watch?v=3OamzN90kPg&ab_channel=NeetCode







