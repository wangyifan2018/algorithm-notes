```py
class Solution:
    def cuttingRope(self, n: int) -> int:
        if n < 4: return n - 1
        res = 1
        while n > 4:
            if res == 1:
                res = 3
            else:
                res *= 3
            n -= 3

        return res * n % (1000000007)
```        
