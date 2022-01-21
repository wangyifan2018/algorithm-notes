```js
/**
 * @param {number[]} nums
 * @return {number}
 */
var maxSubArray = function(nums) {
    let res = nums[0];
    let dp = new Array(nums.length);
    dp[0] = nums[0];
    for (let i = 1; i < nums.length; ++i) {
        if (dp[i - 1] > 0) {
            dp[i] = dp[i - 1] + nums[i];
        }
        else {
            dp[i] = nums[i];
        }
        res = Math.max(res, dp[i]);
    }
    return res;
};
```
优化，一个变量
```js
/**
 * @param {number[]} nums
 * @return {number}
 */
var maxSubArray = function(nums) {
    let res = nums[0];
    let pre = nums[0];
    for (let i = 1; i < nums.length; ++i) {
        if (pre > 0) {
            pre = pre + nums[i];
        }
        else {
            pre = nums[i];
        }
        res = Math.max(res, pre);
    }
    return res;
};
```
