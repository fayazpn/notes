
2024-06-13 18:43

Level: #medium  

Tags: [[ds algo]] [[arrays & hashing]]

##### Approach 1

Using de-limiters
We use de-limiters like *#* which will help us identify the separation between each words, but what if the string itself contains a # as the problem statement says the string can contain any ASCII value,

So we take an approach where we embed the length of every string before the word and put a de-limiter,
We don't use the number itself as a de-limiter as it can cause a case of having strings of length double digits,

So we encode strings with length of the string followed by the *#* during the encoding,
In decoding we read the number till *#* and take out the letters in the encoded string for extraction

Algorithm - encode:
- Initialize *result* string with empty value
- Loop through the array
	- Add the *result* string with *len(string)* + *delimiter #* + *string*
- return *result*

Algorithm - decode:
- Initialize *result* array and *i* as current position in string to 0
- Loop through each character in the *str*, until length of *str*  < *i*
	- Initialize *j* which will find total length, set it to i
	- Loop until *str* is '#'
		- It is guaranteed that 1st char will be number
		- If not increment *j* by 1
	- Initialize *length* variable which is equal to *string from i to j*
	- Slice string from *j + 1* to *length*
	- Append the sliced string to the *result* array
	- Update *i* to *length*

```python
class Solution:

	"""
	
	@param: strs: a list of strings
	
	@return: encodes a list of strings to a single string.
	
	"""
	
	def encode(self, strs):
		resultstr = ''
		
		for string in strs:
			
			resultstr += str(len(string)) + '#' + string
		return resultstr

"""

@param: str: A string

@return: decodes a single string to a list of strings

"""

def decode(self, str):
	
	result, i = [], 0
	while i < len(str):
		j = i
		while str[j] != '#':
			j += 1
		
		length = int(str[i:j])
		
		result.append(str[j + 1: j + 1 +length])
		
		i = j + 1 + length
	
	return result
```

# References

Youtube video link - https://www.youtube.com/watch?v=B1k_sxOSgv8&ab_channel=NeetCode






