```python
class Solution:
    def fib(self, n: int) -> int:
        pre = 0
        cur = 1
        for _ in range(n):
            pre, cur = cur, pre + cur
        return pre % 1000000007
```        
