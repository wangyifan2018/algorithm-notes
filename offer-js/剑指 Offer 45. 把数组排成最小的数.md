```py
class Solution:
    def minNumber(self, nums: List[int]) -> str:
        def quicksort(l, r):
            if l >= r:
                return
            i, j = l, r
            while i < j:
                while strs[l] + strs[j] <= strs[j] + strs[l] and i < j: j -= 1
                while strs[i] + strs[l] <= strs[l] + strs[i] and i < j: i += 1
                strs[i], strs[j] = strs[j], strs[i]
            strs[l], strs[i] = strs[i], strs[l]
            quicksort(l, i - 1)
            quicksort(i + 1, r)

        strs = [str(num) for num in nums]
        quicksort(0, len(strs) - 1)
        return ''.join(strs)
```        
