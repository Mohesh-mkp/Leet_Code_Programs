# Two Sum

Given an array of integer nums and an integer target, return indices of the two numbers such that they add up to target.    
You may assume that each input would have exactly one solution, and you may not use the same element twice.    
You can return the answer in any order.    

Example 1:

Input: nums = [2,7,11,15], target = 9    
Output: [0,1]    
Explanation: Because nums[0] + nums[1] == 9, we return [0, 1].    

Example 2:    

Input: nums = [3,2,4], target = 6     
Output: [1,2]

Example 3:   

Input: nums = [3,3], target = 6     
Output: [0,1]     

### Solution

```python
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        for i in range(len(nums)):
                for j in range(i+1,len(nums)):
                    if target == nums[i]+nums[j]:
                        return [i,j]
                    
                    
num = [1,2,3,4,5,6,7,8,9,10]
target = 8

s = Solution()
print(s.twoSum(num,target))
```

## Other methods to have O(n) time complexity:

```python
################# Method - 1 ########################################

class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        num_set = set()
        for num in nums:
            complement = target - num
            if complement in num_set:
                return [nums.index(complement), nums.index(num)]
            num_set.add(num)
        return []  # If no solution is found

# Example usage
num = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
target = 8

s = Solution()
print(s.twoSum(num, target))


######################## Method - 2 #################################

class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        num_dict = {}
        for i, num in enumerate(nums):
            complement = target - num
            if complement in num_dict:
                return [num_dict[complement], i]
            num_dict[num] = i
        return []  # If no solution is found

# Example usage
num = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
target = 8

s = Solution()
print(s.twoSum(num, target))


```
