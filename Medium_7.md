## Reverse an Integer

```
Given a signed 32-bit integer x, return x with its digits reversed.
If reversing x causes the value to go outside the signed 32-bit
integer range [-231, 231 - 1], then return 0.

Assume the environment does not allow you to store 64-bit integers (signed or unsigned).

Example 1:

Input: x = 123
Output: 321
Example 2:

Input: x = -123
Output: -321
Example 3:

Input: x = 120
Output: 21

Constraints:

-231 <= x <= 231 - 1
```


```python
class Solution:
    def reverse(self, x: int) -> int:
        result = 0
        if x > 0:
            result = Solution.res(x)
        else:
            x = 0 - x
            result = 0 - Solution.res(x)
        
        if result >= -2**31 and result <= 2**31 - 1 and x >= -2**31 and x <= 2**31 - 1:
            return result
        else:
            return 0
        
    def res(x):
        res = 0
        while True:
            res = res * 10 + (x%10)
            x = x // 10
            if x == 0:
                break
        return res

```
