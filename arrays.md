#arrays

+ [Two-sum](#two-sum)
+ [3sum](#3sum)
+ [subarray-sum-equals-k](#subarray-sum-equals-k)


##Two-sum

https://leetcode.com/problems/two-sum/

```python
def twoSum(self, nums: List[int], target: int) -> List[int]:
    comp_sum = {}
    for i in range(len(nums)):
        required = target - nums[i]
        if required in comp_sum:
            return [comp_sum[required], i]
        comp_sum[nums[i]] = i
    return []

```