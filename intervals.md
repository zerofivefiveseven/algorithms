# Intervals

+[Insert Interval](#insert-interval)
+[Merge Intervals](#merge-intervals)
+[Non-overlapping Intervals](#non-overlapping-intervals)

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

## Merge Intervals

https://leetcode.com/problems/merge-intervals/

```python
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