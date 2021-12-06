```python
class Solution:
    def myPow(self, x: float, n: int) -> float:
        def quick(n):
            if n == 0:
                return 1
            if abs(n) == 1:
                return x**n
            res = quick(n//2)
            res *= res
            if n % 2 == 1:
                res *= x
            return res
        return quick(n)
```        
