# Arrays
 
 + [Two sum](#two-sum)
 + [3 Sum](#3sum)
 + [Subarray Sum Equals K](#subarray-sum-equals-k)

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
 
 ## Subarray Sum Equals K

 https://leetcode.com/problems/subarray-sum-equals-k/

 ```python
 def subarraySum(self, nums, k: int):
        prefsumToFreaqDict={0 : 1}
        sum = 0
        counter = 0
        for index in range(len(nums)):
            sum += nums[index]
            if sum - k in prefsumToFreaqDict:
                counter += prefsumToFreaqDict.get(sum - k)
            prefsumToFreaqDict[sum]= prefsumToFreaqDict.pop(sum, 0) + 1
        return counter
 ```