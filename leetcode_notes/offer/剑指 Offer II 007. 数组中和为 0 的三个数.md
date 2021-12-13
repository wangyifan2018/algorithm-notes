```python
class Solution:
    def threeSum(self, nums: List[int]) -> List[List[int]]:
        n = len(nums)
        res = []
        nums.sort()
        for i in range(0, n - 2):
            if nums[i] > 0:
                return res
            if i > 0 and nums[i] == nums[i - 1]:
                continue
            left, right = i + 1, n - 1        
            while left < right:
                total = nums[i] + nums[left] + nums[right]
                if total == 0:
                    res.append([nums[i], nums[left], nums[right]])
                    val = nums[left]
                    while left < right and nums[left] == val:
                        left += 1
                elif total > 0:
                    right -= 1
                else:
                    left += 1
        return res
```        
