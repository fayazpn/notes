
2024-09-15 12:18

Status: #child 

Tags: [[ds algo]] [[algorithm]] [[two pointers]]

# Leetcode 125 - Valid Palindrome

```python    
class Solution:
    def isPalindrome(self, s: str) -> bool:
        l, r = 0, len(s) - 1
        while l < r:
            # while l < r and not self.isAlphaNum(s[l]) or self.isAlphaNum(s[r]):
            #     if(not self.isAlphaNum(s[l])):
            #         l += 1
                
            #     if(not self.isAlphaNum(s[r])):
            #         r -= 1
            while l < r and not self.isAlphaNum(s[l]):
                l += 1
            
            while l < r and not self.isAlphaNum(s[r]):
                r -= 1
            
            if s[l].lower() != s[r].lower():
                return False
            l += 1
            r -= 1
            
        return True   


    def isAlphaNum(self, c: str) -> bool:
        return ord('0') <= ord(c) <= ord('9') or ord('a') <= ord(c) <= ord('z') or ord('A') <= ord(c) <= ord('Z') 
```

- commented out code makes unnecessary iterations and potentially moves both pointers in a single iteration
- 
# References






