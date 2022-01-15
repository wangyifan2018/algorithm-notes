```python
/**
 * @param {string} s
 * @param {number} n
 * @return {string}
 */
var reverseLeftWords = function(s, n) {
    let newStr = ''
    newStr += s.slice(n, s.length)
    newStr += s.slice(0, n)
    return newStr
};
```
