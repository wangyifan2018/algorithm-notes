```python
class Solution:
    def findRepeatNumber(self, nums: List[int]) -> int:
        dep = set()
        for num in nums:
            if num in dep:
                return num
            else:
                dep.add(num)
        return
```
