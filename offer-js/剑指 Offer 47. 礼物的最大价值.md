```js
/**
 * @param {number[][]} grid
 * @return {number}
 */
var maxValue = function(grid) {
    let dp = new Array(grid[0].length);
    dp[0] = grid[0][0];
    for (let i = 1; i < grid[0].length; ++i) {
        dp[i] = grid[0][i] + dp[i - 1];
    }

    for (let j = 1; j < grid.length; ++j) {
        dp[0] = dp[0] + grid[j][0];
        for (let i = 1; i < grid[0].length; ++i) {
            dp[i] = Math.max(dp[i - 1] + grid[j][i], dp[i] + grid[j][i]);
        }
    }

    return dp.slice(-1);
};
```
