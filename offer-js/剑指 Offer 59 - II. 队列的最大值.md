```py
class MaxQueue:
    def __init__(self):
        self.q = deque()
        self.maxq = deque()

    def max_value(self) -> int:
        if self.maxq:
            return self.maxq[0]
        else:
            return -1

    def push_back(self, value: int) -> None:
        while self.maxq and self.maxq[-1] < value:
            self.maxq.pop()
        self.maxq.append(value)
        self.q.append(value)

    def pop_front(self) -> int:
        if self.q:
            res = self.q.popleft()
            if res == self.maxq[0]:
                self.maxq.popleft()
            return res
        else:
            return -1



# Your MaxQueue object will be instantiated and called as such:
# obj = MaxQueue()
# param_1 = obj.max_value()
# obj.push_back(value)
# param_3 = obj.pop_front()
```
