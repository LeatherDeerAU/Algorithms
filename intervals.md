#intervals

+ [Non-overlapping intervals](#non-overlapping-intervals)
+ [Merge Intervals](#merge-intervals)
+ [Insert Interval](#insert-interval)


##Non-overlapping intervals

https://leetcode.com/problems/non-overlapping-intervals/# 

```python
def eraseOverlapIntervals(self, intervals: List[List[int]]) -> int:
    intervals.sort(key=lambda x: x[0])
    ans = 0
    prev = float('-inf')
    for interval in intervals:
        if interval[0] >= prev:
            prev = interval[1]
        else:
            ans += 1
            prev = min(prev, interval[1])
    return ans

```

##Merge Intervals

https://leetcode.com/problems/merge-intervals/#

```python
def merge(self, intervals: List[List[int]]) -> List[List[int]]:
    intervals.sort(key=lambda x: x[0])
    res = []
    if len(intervals) > 0:
        res.append(intervals[0])
    for i in range(1, len(intervals)):
        if intervals[i][0] <= res[-1][1]:
            if res[-1][-1] > intervals[i][-1]:
                continue
            else:
                res[-1].pop(-1)
                res[-1].append(intervals[i][-1])
        else:
            res.append(intervals[i])
    return res
    
```

##Insert Interval

https://leetcode.com/problems/insert-interval/#

```python
def insert(self, intervals: List[List[int]], newInterval: List[int]) -> List[List[int]]:
    intervals.append(newInterval)
    intervals.sort(key=lambda x: x[0])
    res = []
    if len(intervals) > 0:
        res.append(intervals[0])
    for i in range(1, len(intervals)):
        if intervals[i][0] <= res[-1][1]:
            if res[-1][-1] > intervals[i][-1]:
                continue
            else:
                res[-1].pop(-1)
                res[-1].append(intervals[i][-1])
        else:
            res.append(intervals[i])
    return res

```