```python
class Solution:
    def strStr(self, haystack: str, needle: str) -> int:
        if not haystack and not needle:
            return 0
        if not haystack or len(haystack) < len(needle):
            return -1
        if not needle:
            return 0
        hash_val = 0
        target = 0
        prime = 101
        for i in range(len(haystack)):
            if i < len(needle):
                hash_val = hash_val * 26 + (ord(haystack[i]) - ord("a"))
                target = target * 26 + (ord(needle[i]) - ord("a"))
            else:
                hash_val = (
                    hash_val - (ord(haystack[i - len(needle)]) - ord("a")) * 26 ** (len(needle) - 1)
                ) * 26 + (ord(haystack[i]) - ord("a"))
            if i >= len(needle) - 1 and hash_val == target :
                return i - len(needle) + 1
        return -1
```        
