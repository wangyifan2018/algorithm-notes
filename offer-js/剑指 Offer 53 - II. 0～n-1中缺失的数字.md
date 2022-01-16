```js
/**
 * @param {number[]} nums
 * @return {number}
 */
var missingNumber = function(nums) {
    let n = nums.length, ans = n;
    for (let i = 0; i < n; i++) {
        if (nums[i] != i) {
            ans = i;
            break;
        }
    }
    return ans;
};
```
