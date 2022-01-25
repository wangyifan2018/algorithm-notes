```py
class Solution:
    def reverseWords(self, s: str) -> str:
        left, right = 0, len(s) - 1
        while left < right and s[left] == ' ':
            left += 1
        while left < right and s[right] == ' ':
            right -= 1
        
        q = collections.deque()

        tmp = ''
        while left <= right:
            if s[left] == ' ' and len(tmp) != 0:
                q.appendleft(tmp)
                tmp = ''
            elif s[left] != ' ':
                tmp += s[left]
            left += 1
        q.appendleft(tmp)
        return ' '.join(q)
        
```

```py
class Solution:
    def reverseWords(self, s: str) -> str:
        s = s.strip()
        left, right = len(s) - 1, len(s) - 1
        res = []
        while left >= 0:
            while left >= 0 and s[left] != ' ':
                left -= 1
            res.append(s[left + 1 : right + 1])
            while s[left] == ' ':
                left -= 1
            right = left

        return ' '.join(res)
        
```                
