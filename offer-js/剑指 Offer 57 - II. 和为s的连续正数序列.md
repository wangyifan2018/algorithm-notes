```py
class Solution:
    def findContinuousSequence(self, target: int) -> List[List[int]]:
        left, right = 1, 1
        tmp = 0
        res = []
        while left <= target // 2:
            if tmp < target:
                tmp += right
                right +=1
            elif tmp > target:
                tmp -= left
                left += 1
            else:
                res.append(list(range(left, right)))
                tmp -= left
                left += 1
        return res
```
