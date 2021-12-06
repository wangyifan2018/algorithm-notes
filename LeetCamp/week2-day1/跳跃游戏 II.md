```python
class Solution:
    def jump(self, nums: List[int]) -> int:
        r = 0
        steps = [0]
        for i, num in enumerate(nums):
            nr = min(i + num, len(nums) - 1)
            if nr <= r:
                continue
            else:
                for _ in range(r + 1, nr + 1):
                    steps.append(steps[i] + 1)
                r = nr
        return steps[len(nums) - 1]
```        
