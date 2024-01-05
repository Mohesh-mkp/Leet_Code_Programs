# Find the Index of the First Occurrence in a String
[Detailed description here](https://leetcode.com/problems/find-the-index-of-the-first-occurrence-in-a-string/description/)    

### Solution:
```python

class Solution:
    def strStr(self, haystack: str, needle: str) -> int:
        if len(needle) > len(haystack) or needle not in haystack:
            return -1
        elif len(needle) == len(haystack) and needle == haystack:
            return 0

        else:
            for i in range(len(haystack)-len(needle)+1):
                if haystack[i:i+len(needle)] == needle:
                    return i

```
