```py
class Solution:
    def majorityElement(self, nums: List[int]) -> int:
        x, vote = 0, 0
        for num in nums:
            if (vote == 0): x = num
            vote += 1 if x == num else -1
        return x
```
