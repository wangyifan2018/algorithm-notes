```js
/**
 * @param {number} n
 * @return {number}
 */
var fib = function(n) {
    if (n === 0) {
        return 0;
    }
    let pre = 0, cur = 1;
    for (let i = 0; i < n; ++i) {
        let tmp = (cur + pre) % 1000000007;
        pre = cur;
        cur = tmp;
    }
    return pre ;
};
```
