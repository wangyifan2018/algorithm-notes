```js
/**
 * @param {number[]} nums
 * @return {number}
 */
var findRepeatNumber = function(nums) {
    let i = 0, n = nums.length;
    while (i < n) {
        if (nums[i] == i) {
            i++;
            continue;
        }


        if (nums[nums[i]] == nums[i]) {
            return nums[i]
        }
        let tmp = nums[nums[i]];
        nums[nums[i]] = nums[i];
        nums[i] = tmp;

    }
    return -1
};
```
