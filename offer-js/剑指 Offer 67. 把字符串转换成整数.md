```py
class Solution:
    def strToInt(self, str: str) -> int:
        if not str: return 0
        res, i, sign, length = 0, 0, 1, len(str)
        int_max, int_min, binary = 2 ** 31 - 1, - 2 ** 31, 2 ** 31 // 10
        while i < length:
            if str[i] == ' ':
                i += 1
            else:
                break
            if i == length: return 0
        if str[i] == '-': sign = -1
        if str[i] in '+-': i += 1

        for c in str[i::]:
            if not ord('0') <= ord(c) <= ord('9'): break
            if res > binary or res == binary and res * 10 + ord(c) - ord('0') > int_max: return int_max if sign == 1 else int_min
            res = res * 10 + ord(c) - ord('0')
        
        return sign * res

```
