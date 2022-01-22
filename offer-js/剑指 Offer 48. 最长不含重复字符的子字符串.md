滑窗
```py
class Solution:
    def lengthOfLongestSubstring(self, s: str) -> int:
        n = len(s)
        left, right = 0, 0
        has = set()
        res = 0
        while right < n:
            if s[right] not in has:
                has.add(s[right])
                res = max(res, right - left + 1)
                right += 1
            else:
                while s[left] != s[right]:
                    has.remove(s[left])
                    left += 1
                
                left += 1
                right += 1
        return res
```
动态规划
```py
class Solution:
    def lengthOfLongestSubstring(self, s: str) -> int:
        dic = {}
        res = tmp = 0
        for j in range(len(s)):
            i = dic.get(s[j], -1)
            dic[s[j]] = j
            tmp = tmp + 1 if tmp < j - i else j - i
            res = max(res, tmp)
        return res
 

```
