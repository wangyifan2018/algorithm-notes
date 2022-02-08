```py
class Solution:
    def maxSlidingWindow(self, nums: List[int], k: int) -> List[int]:
        if not nums:
            return []
        
        q = deque()
        res = []

        for i in range(k):
            while q and nums[q[-1]] <= nums[i]:
                q.pop()
            q.append(i)

        res.append(nums[q[0]])

        for i in range(k, len(nums)):
            while q and nums[q[-1]] <= nums[i]:
                q.pop()
            q.append(i)
            while q[0] <= i - k:
                q.popleft()
            res.append(nums[q[0]])
 
        return res
```
