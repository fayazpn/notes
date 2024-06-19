
2024-06-11 14:39

Level: #easy

Tags: [[ds algo]] [[arrays & hashing]]

# Arrays & Hashing

**Approach 1**

- Using brute force method, where we init two loops and try to check if it adds up to the target
- **Time Complexity - *O(n^2)***
- **Space Complexity - *O(1)***

**Approach 2**

Using hash-map

- Initialize hash-map
- Loop though the array with index
- Index the element and store the array index as the value of the hash-map
- Check if the result of "target - array element " is present in the hash-map lookup key
	- if true, return "(index, hash-map lookup value )"
	- else store the array element as the key and index as the value
- if no such returns return empty array

```python
class Solution(object):

	def twoSum(self, nums, target):
	
		"""
		
		:type nums: List[int]
		
		:type target: int
		
		:rtype: List[int]
		
		"""
		hashmap = {}
		
		for i in range(0, len(nums)):
			second = target - nums[i]
			if(second in hashmap):
				return [i,hashmap[second]]
			else:
				hashmap[nums[i]] = i
		return []
```

**Time Complexity - *O(n)***
**Space Complexity - *O(n)***
# References

Youtube Video Solution: https://www.youtube.com/watch?v=KLlXCFG5TnA&ab_channel=NeetCode






