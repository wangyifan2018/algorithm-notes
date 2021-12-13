```python
class Solution:
    def minSubArrayLen(self, target: int, nums: List[int]) -> int:
        n = len(nums)
        start, end = 0, 0
        total = 0
        res = n + 1
        while end < n:
            total += nums[end]
            while total >= target:
                res = min(res, end - start + 1)
                total -= nums[start]
                start += 1
            end += 1
        return 0 if res == n + 1 else res
```
