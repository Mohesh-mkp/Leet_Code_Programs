# Add Binary

Given two binary strings a and b, return their sum as a binary string.

Example 1:

Input: a = "11", b = "1"   
Output: "100"

Example 2:   

Input: a = "1010", b = "1011"    
Output: "10101"    

[Detailed description here](https://leetcode.com/problems/add-binary/description/)

```python
'''class Solution:
    def addBinary(self, a: str, b: str) -> str:
        res = int(a,2) + int(b,2)
        res = str(bin(res)[2:])
        return res
'''
class Solution:
    def addBinary(self, a: str, b: str) -> str:
        return str(bin(int(a,2) + int(b,2))[2:])

```
