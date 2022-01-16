```python
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number}
 */
var search = function(nums, target) {
    var helper = function(nums, tar) {
        let i = 0, j = nums.length - 1;
        while (i <= j) {
            const m = Math.floor((i + j) / 2);
            if (nums[m] <= tar) {
                i = m + 1;
            }
            else {
                j = m - 1;
            }
        }
        return i;
    }
    const rightidx = helper(nums, target), leftidx = helper(nums, target-1);
    return rightidx - leftidx
};
```
