
2024-06-14 20:31

Level: #medium 

Tags: [[ds algo]] [[arrays & hashing]]

# Arrays & Hashing

- In imaginary number-line, check the start of sequence
- Initialize *longest* variable with 0 as its initial value
- Convert the list to a set for O(1) average-time complexity for membership checks
- Loop through the input array
	- To check the start of the sequence, check if the number before *n-1* belongs in the array
		- If not it does not qualify as the sequence start
		- Else it qualifies
	- Once an element in the input array qualifies as sequence starter, initialize *length* variable to 0
	- Loop until the number next to it in the imaginary number line belongs in the input array
		- If not, compare the max between *longest* & *length* and assign the max to the *longest*
		- Each number in the input array is part of this loop at most once only. So it is not **O(n^2)** complexity
	- Return *longest* variable


```python
class Solution(object):
    def longestConsecutive(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        longest = 0
        numSet = set(nums)
        for i in nums:
            if i - 1 not in numSet:
                length = 0
                while i + length in numSet:
                    length += 1
                longest = max(longest, length)
                
        return longest
```







# References

Youtube video solution - https://www.youtube.com/watch?v=P6RZZMu_maU





