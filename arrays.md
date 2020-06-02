# Arrays
 
 + [Two sum](#two-sum)
 
 ## Two sum

 https://leetcode.com/problems/two-sum/

 ```python
 def twoSum(self, nums, target):
    if len(nums) <= 1:
        return False
    buffer_dictionary = {}
    for i in range(len(nums)):
        if nums[i] in buffer_dictionary:
            return [buffer_dictionary[nums[i]], i]
        else:
            buffer_dictionary[target - nums[i]] = i       
 ```