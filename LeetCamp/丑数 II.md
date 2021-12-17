```python
class Solution:
    def nthUglyNumber(self, n: int) -> int:
        factors = [2, 3, 5]
        heap = [1]
        seen = {1}

        for i in range(n - 1):
            cur = heapq.heappop(heap)
            for fact in factors:
                if (nxt := cur * fact) not in seen:
                    seen.add(nxt)
                    heapq.heappush(heap, nxt)
        return heapq.heappop(heap)
```        
