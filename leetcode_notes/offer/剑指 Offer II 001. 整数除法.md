```python
class Solution:
    def divide(self, a: int, b: int) -> int:
        flag = False if (a > 0 and b > 0) or (a < 0 and b < 0) else True
        x, y = abs(a), abs(b)

        def cal(x, y):
            n = 1
            while x > y << 1:
                y <<= 1
                n <<= 1
            return n, y
        
        res = 0
        while x >= y:
            cnt, val = cal(x, y)
            x -= val
            res += cnt
        if flag:
            res = -res
        return res if res < 2 ** 31 else res - 1
```        
