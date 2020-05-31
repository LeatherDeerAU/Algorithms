#intervals

+ [Non-overlapping intervals](#non-overlapping-intervals)


##Non-overlapping intervals

https://leetcode.com/problems/non-overlapping-intervals/# 

```python
def eraseOverlapIntervals(self, intervals: List[List[int]]) -> int:
    intervals.sort()
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