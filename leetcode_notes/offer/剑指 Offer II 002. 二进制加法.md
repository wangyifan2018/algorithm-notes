```python
class Solution:
    def addBinary(self, a: str, b: str) -> str:
        res = ''
        i1, i2, carry = len(a) - 1, len(b) - 1, 0
        while i1 >= 0 or i2 >= 0:
            x = ord(a[i1]) - ord('0') if i1 >= 0 else 0
            y = ord(b[i2]) - ord('0') if i2 >= 0 else 0
            sum = x + y + carry
            carry = sum // 2
            res += str(sum % 2)
            i1 -= 1
            i2 -= 1
        if carry:
            res += str(carry)
        return res[::-1]
```        
