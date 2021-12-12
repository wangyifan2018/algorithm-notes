```python
class Solution:
    def singleNumber(self, nums: List[int]) -> int:
        cnt = {}
        for num in nums:
            cnt[num] = cnt.get(num, 0) + 1
        for key, values in cnt.items():
            if values == 1:
                return key
        return key
```        
