
## Rotate an array:

[Detailed description here](https://leetcode.com/problems/rotate-array/)      

Given an integer array nums, rotate the array to the right by k steps, where k is non-negative.

| Example | Input                     | Output                  | Explanation                                     |
|---------|---------------------------|-------------------------|-------------------------------------------------|
| 1       | nums = [1,2,3,4,5,6,7], k = 3 | [5,6,7,1,2,3,4]         | Rotate 1 step: [7,1,2,3,4,5,6]                 |
|         |                           |                         | Rotate 2 steps: [6,7,1,2,3,4,5]                |
|         |                           |                         | Rotate 3 steps: [5,6,7,1,2,3,4]                |
| 2       | nums = [-1,-100,3,99], k = 2 | [3,99,-1,-100]          | Rotate 1 step: [99,-1,-100,3]                   |
|         |                           |                         | Rotate 2 steps: [3,99,-1,-100]                 |
| 3       | nums = [1,2], k = 3        | [2,1]                   | Rotate 1 step: [2,1]                            |
|         |                           |                         | Rotate 2 steps: [1,2]                          |
|         |                           |                         | Rotate 3 steps: [2,1]                          |
| 4       | nums = [-1], k = 2         | [-1]                    | Rotate 1 step: [-1]                            |
|         |                           |                         | Rotate 2 steps: [-1]                           |


## Solution

```python

class Solution:
    def rotate(self, nums: list[int], K: int) -> None:
        """
        Do not return anything, modify nums in-place instead.
        """
        k = self.check_k(K,len(nums))
        i = 0
        while i < len(nums)-i-1:
            nums[i], nums[len(nums)-i-1] = nums[len(nums)-i-1], nums[i]
            i += 1
        nums[0:k], nums[k::] = nums[0:k][::-1], nums[k::][::-1]
    
    def check_k(self,num1, num2):
        while num1 > num2 and num2 > 1:
            num1 -= num2
            return self.check_k(num1, num2)
        return num1

```
