# Arrays
 
 + [Subarray Sum Equals K](#subarray-sum-equals-k)
 
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
 