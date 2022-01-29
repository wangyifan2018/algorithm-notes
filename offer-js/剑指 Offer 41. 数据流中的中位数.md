```py
class MedianFinder:

    def __init__(self):
        """
        initialize your data structure here.
        """
        self.A = []
        self.B = []

    def addNum(self, num: int) -> None:
        if len(self.A) != len(self.B):
            heapq.heappush(self.A, -num)
            heapq.heappush(self.B, -heapq.heappop(self.A))
        else:
            heapq.heappush(self.B, num)
            heapq.heappush(self.A, -heapq.heappop(self.B))

    def findMedian(self) -> float:
        if len(self.A) != len(self.B):
            return -self.A[0]
        else:
            return (-self.A[0] + self.B[0]) / 2


# Your MedianFinder object will be instantiated and called as such:
# obj = MedianFinder()
# obj.addNum(num)
# param_2 = obj.findMedian()
```
