#arrays

+ [Two-sum](#two-sum)
+ [3sum](#3sum)
+ [subarray-sum-equals-k](#subarray-sum-equals-k)


##Two-sum

https://leetcode.com/problems/two-sum/#

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

##3sum

https://leetcode.com/problems/3sum/#

```python
def threeSum(self, nums: List[int]) -> List[List[int]]:
    ans = set()
    nums.sort()
    for i in range(0, len(nums) - 2):
        mp = set()
        required = 0 - nums[i]
        for j in range(i + 1, len(nums)):
            complement = required - nums[j]
            if complement not in mp:
                mp.add(nums[j])
            else:
                ans.add((nums[i], nums[j], complement))
    return list(ans)

```

##subarray-sum-equals-k

https://leetcode.com/problems/subarray-sum-equals-k/#

```python
def subarraySum(self, nums: List[int], k: int) -> int:
    dict = {}
    sum = count = 0
    dict[0] = 1
    for i in range(len(nums)):
        sum += nums[i]
        if sum - k in dict:
            count += dict[sum - k]
        if sum in dict:
            dict[sum] += 1
        else:
            dict[sum] = 1
    return count

```
