
- Check if two of the strings are equal in length
	- if not return False
- Create a hashmap ds, each char will be key and rep will be the value
- Fill the hashmap with string 't' incrementing value if char is repeated
- In the same hashmap we decrement the string 's' value
	- if key not found in hashmap return False
- finally loop through the hashmap, check if all the keys values are 0
	- if not return False
- If everything 0, return True

```
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