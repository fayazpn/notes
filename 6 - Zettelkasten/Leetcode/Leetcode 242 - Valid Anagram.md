
2024-06-10 02:23

Level: #easy

Tags: [[ds algo]] [[arrays & hashing]]

# Arrays & Hashing

##### Algorithm
- Init hashmap
- Check if length of both strings are the same
	- if not then return False
- Loop through 1st string
	- create hashmap with key as the letter and values as the count of repetition
- Loop though the 2nd string
	- create hashmap with key as letter and values as count of repetition
- Compare both the hashmaps compare


#### Approach 1

```python
class Solution(object):

	def isAnagram(self, s, t):
	
		"""
		
		:type s: str
		
		:type t: str
		
		:rtype: bool
		
		"""
		
		# If not equal length then return false
		
		hashmap = {}
		
		if len(s) != len(t):
			return False
		
		for i in s:
			if i in hashmap:
				hashmap[i] += 1
			else:
				hashmap[i] = 1
				
		for i in t:
			if i not in hashmap or hashmap[i] == 0:
				return False
			hashmap[i] -= 1
			
		return True
```

**Time Complexity - *O(n)***
 
**Space Complexity - O(n)**

***
##### Approach 2

```python
class Solution(object):
    def isAnagram(self, s, t):
        """
        :type s: str
        :type t: str
        :rtype: bool
        """

        hashmap = {}

        if len(s) != len(t):
            return False

        for i in s:
            if i in hashmap:
                hashmap[i] += 1
            else:
                hashmap[i] = 1

        for i in t:
            if i in hashmap:
                hashmap[i] -= 1
            else:
                return False

        for items in hashmap:
            if hashmap[items] != 0:
                return False
        return True
```


# References

Youtube video link - https://www.youtube.com/watch?v=9UtInBqnCgA&ab_channel=NeetCode





