# Remove duplicate element completely

[Detailed description here](https://leetcode.com/problems/remove-element/description/)

```python
class Solution:
    def removeElement(self, nums: list[int], val: int) -> int:
        my_dict = {}
        for ele in nums:
            if ele not in my_dict:
                my_dict[ele] = 1
            else:
                my_dict[ele] += 1
        
        nums.clear()
        for key,value in my_dict.items():
            if key != val:
                nums.extend([key] * value)
        return nums

l1, val = [0,1,2,2,3,0,4,2], 2
sol = Solution()
print(sol.removeElement(l1, val))

###################################### Using list comprehension ################################
class Solution:
    def removeElement(self, nums: list[int], val: int) -> int:
        nums = [ele for ele in nums if ele != val]
        return nums

l1, val = [0, 1, 2, 2, 3, 0, 4, 2], 2
sol = Solution()
print(sol.removeElement(l1, val))

```
