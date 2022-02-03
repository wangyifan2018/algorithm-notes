```py
class Solution:
    def singleNumber(self, nums: List[int]) -> int:
        count = [0] * 32
        for num in nums:
            for i in range(32):
                count[i] += num & 1
                num >>= 1
        
        res, m = 0, 3
        for i in range(32):
            res <<= 1
            res |= count[31 - i] % m
        return res
```        
