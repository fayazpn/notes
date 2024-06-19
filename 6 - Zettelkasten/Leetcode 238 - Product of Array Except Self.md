
2024-06-14 14:08

Level: #medium 

Tags: [[ds algo]] [[arrays & hashing]]

# Arrays & Hashing

We use the strategy of pre-fix post-fix arrays, but we do it on a single output array
So we will do two passes, on the first pass, we compute the pre-fixes of elements in the array
On the second pass we multiply with post-fix with computed pre-fixes

- Initialize result array
- Initialize *postfix* and *prefix* value storage variables
- Loop through each elements
	- On the first pass if index is 0, *prefix* value is 1
	- On other elements, *prefix* * *currentElement* store it in the current position of the result array
	- On the second pass, on the last element *prefix* init as 1
	- On other elements, *prefix* *  *currentElement* of result array
	- return result array

```python
class Solution(object):

	def productExceptSelf(self, nums):
		
		"""
		
		:type nums: List[int]
		
		:rtype: List[int]
		
		"""
		result, prefix, postfix = [], 1, 1
		
		for i in range(len(nums)):
			
			result.append(prefix)
			prefix *= nums[i]
		
		for i in range(len(nums) - 1, -1, -1):
			
			result[i] *= postfix
			postfix *= nums[i]
		
		return result
```

**Key Takeaways** 
- On the second loop, we give till -1 to cover the first element of the array
- First store the value then do the pre-fix post-fix computation
# References

Youtube video solution - https://www.youtube.com/watch?v=bNvIQI2wAjk&ab_channel=NeetCode





