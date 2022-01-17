```js
/**
 * @param {string} s
 * @return {character}
 */
var firstUniqChar = function(s) {
    const freq = _.countBy(s);
    for (i = 0; i < s.length; i++) {
        if (freq[s[i]] === 1) {
            return s[i];
        }
    }
    return ' '
};
```
