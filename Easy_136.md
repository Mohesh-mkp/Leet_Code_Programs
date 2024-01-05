## To find single element

[Detailed description here](https://leetcode.com/problems/single-number/)    

Given a non-empty array of integers nums, every element appears twice except for one. Find that single one.

You must implement a solution with a linear runtime complexity and use only constant extra space.

 

Example 1:

Input: nums = [2,2,1]    
Output: 1    

Example 2:

Input: nums = [4,1,2,1,2]    
Output: 4    

Example 3:

Input: nums = [1]    
Output: 1

## Solution

```python

class Solution:
    def singleNumber(self, nums: List[int]) -> int:
        '''dup_dcit = {}
        for ele in nums:
            if ele in dup_dcit:
                dup_dcit[ele] += 1
            else:
                dup_dcit[ele] = 1
        
        for key in dup_dcit:
            if dup_dcit[key] == 1:
                return key'''
        result = 0
        for num in nums:
            result ^= num
        return result

```

