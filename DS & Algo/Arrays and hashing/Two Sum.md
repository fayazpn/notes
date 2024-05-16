
- Create hash map
- Loop through every element in the array
- Subtract current element from the target
	- Check if if the result is present in the hash map keys,
		- if present return values of current element and value of the result in the hash map
		- if not add it to the HashMap

```
	hashmap = {}

	for i in range(len(nums)):
		 result = target - nums[i]
		if(result in hashmap):
			print(hashmap[result], i)
		else:
			hashmap[num[i]] = i
```