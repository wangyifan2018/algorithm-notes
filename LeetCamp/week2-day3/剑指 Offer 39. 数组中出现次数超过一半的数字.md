```python
class Solution:
    def majorityElement(self, nums: List[int]) -> int:
        n = len(nums)
        half = n / 2
        cnt = {}
        for num in nums:
            cnt[num] = cnt.get(num, 0) + 1
        for key, value in cnt.items():
            if value > half:
                return key
        return nums[0]
```        
