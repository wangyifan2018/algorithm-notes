```js
/**
 * @param {number} n
 * @return {number}
 */
var numWays = function(n) {
    let pre = 1, cur = 1;
    for (let i = 0; i < n; ++i) {
        let tmp = (pre + cur) % 1000000007;
        pre = cur;
        cur = tmp;
    }
    return pre;

};
```
