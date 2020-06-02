 # Intervals
 
+ [Non-overlapping Intervals](#non-overlapping-intervals)
 
## Non-overlapping Intervals

 https://leetcode.com/problems/non-overlapping-intervals/ 

 ```python
 def eraseOverlapIntervals(self, intervals: List[List[int]]) -> int:
     intervals.sort(key=lambda x: x[1])
     lastValidIndex = 0
     intervalsRemoved = 0
     for i in range(1, len(intervals)):
         if  intervals[lastValidIndex][1] > intervals[i][0]:
             intervalsRemoved += 1
         else:
             lastValidIndex = i
     return intervalsRemoved
 ```