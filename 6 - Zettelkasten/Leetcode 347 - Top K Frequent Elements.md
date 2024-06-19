
2024-06-12 00:52

Level: #medium

Tags: [[ds algo]] [[arrays & hashing]]

# Arrays & Hashing

**Approach 1** - Bucket sort
- Not the usual bucket sort, here we are are making bucket sort where index is based on the repetition of the elements
- Can be done with solution such as memory heap but here we take best approach of *O(n)*
- Init a *dict* which takes count of all the letters
- Create a nested array where the number of nested arrays is length of total elements
- Loop through the items of the hash-map
	- In the index of *count_of_number*, append the *number_element*
- Create a *result_array* that should return the **k** most frequent element
- Loop through the nested array in reverse order to get the **most count**
	- On each nested array loop again
		- Add elements to the *result_array* until the array length is equal to **k**

```python
class Solution(object):
    def topKFrequent(self, nums, k):
        """
        :type nums: List[int]
        :type k: int
        :rtype: List[int]
        """
        hashmap = {}

        bucket = [[] for i in range(len(nums) + 1)]

        for i in nums:
            hashmap[i] = 1 + hashmap.get(i, 0)

        for item_key, item_value in hashmap.items():
            bucket[item_value].append(item_key)

        result_array = []

        for item in range(len(bucket) - 1, 0, -1):
            for number in bucket[item]:
                result_array.append(number)            
                if len(result_array) == k:
                    return result_array
```



# References

Youtube video link - https://www.youtube.com/watch?v=YPTqKIgVk-k&ab_channel=NeetCode






