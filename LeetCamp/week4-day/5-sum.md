```python
class Solution:
    def five_sum(self, nums: List[int], target: int) -> bool:
        def dfs(idx,take,s):
            if idx==len(nums):
                if s==target and take==5:
                    return True
                return False
            if take==5:
                return s==target
            if s+sum(nums[idx:])<target or take+len(nums)-idx<5 or s>target:
                return False
            return dfs(idx+1,take+1,s+nums[idx]) or dfs(idx+1,take,s)
        return dfs(0,0,0)

```
