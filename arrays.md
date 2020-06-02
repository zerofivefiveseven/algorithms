# Arrays
 
 + [3 Sum](#3sum)
 
 ## 3 Sum

 https://leetcode.com/problems/3sum/

 ```python
 def threeSum(self, nums):
    nums, i, result = sorted(nums), 0, []
    while i < len(nums) and nums[i] <= 0:   
        dic, target, j = {}, - nums[i], i+1
        while j < len(nums):
            if nums[j] in dic:
                idx = dic[nums[j]]
                result.append([nums[i], nums[idx], nums[j]])
                while i < len(nums) - 1 and nums[i] == nums[i+1]:  i += 1
                while j < len(nums) - 1 and nums[j] == nums[j+1]:  j += 1
            else: dic[target - nums[j]] = j
            j += 1
        i += 1
    return result
 ```
 