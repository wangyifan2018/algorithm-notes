```js
/**
 * @param {number[]} prices
 * @return {number}
 */
var maxProfit = function(prices) {
    if (prices.length == 0) {
        return 0;
    }
    let minNum = prices[0], res = 0;
    for (let i = 0; i < prices.length; ++i) {
        res = Math.max(res, prices[i] - minNum);
        if (prices[i] < minNum) {
            minNum = prices[i];
        }
    }
    return res;
};
```
