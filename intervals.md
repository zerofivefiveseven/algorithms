 # Intervals
 
 + [Insert Interval](#insert-interval)

 ## Insert Interval

 https://leetcode.com/problems/insert-interval/

 ```python
 def insert(self, intervals, newInterval):
     intervals.append(newInterval)
     return self.merge(intervals)

 def merge(self, intervals: List[List[int]]) -> List[List[int]]:
     if not intervals:
         return []
     intervals.sort(key=lambda key: key[0])
     merged = [intervals[0]]
     for interval in intervals[1:]:
         edge = merged[-1]
         if interval[0] > edge[1]:
             merged.append(interval)
         else:
             merged[-1][1] = max(edge[1], interval[1])
     return merged
 ```
