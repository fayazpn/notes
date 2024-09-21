
2024-09-14 23:58

Level: #medium 

Tags: [[ds algo]] [[two pointers]]

# Leetcode 167 - Two Sum II

*Constraint is we should not use extra memory*

**Approach 1**

```python
	class Solution:
	    def twoSum(self, numbers: List[int], target: int) -> List[int]:
	        l, r = 0, len(numbers) - 1
	
	        while l < r:
	            while l < r:
	                if numbers[r] + numbers[l] == target:
	                    return [l + 1, r + 1]
	                r -= 1
	            l += 1
	            r = len(numbers) - 1
	        
	        return []
```
- Nested loop with time complexity *O(n^2)*

***

**Approach 2**

```python
class Solution:
    def twoSum(self, numbers: List[int], target: int) -> List[int]:
        l, r = 0, len(numbers) - 1

        while l < r:
            current_sum = numbers[r] + numbers[l]
            if current_sum == target:
                return [l + 1, r + 1]
            elif current_sum < target:
                l += 1
            else:
                r -= 1
        
        return []
```
- Single loop 
- Calculate the *current sum* and check if it is equal to *target* 
	- if equal then return the index
	- if *target* less than *current sum*
		- decrease the right index by 1
	- else
		- increase the left by 1
# References






