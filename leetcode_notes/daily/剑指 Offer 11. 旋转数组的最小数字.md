```js
/**
 * @param {number[]} numbers
 * @return {number}
 */
var minArray = function(numbers) {
    let left = 0, right = numbers.length - 1;
    while (left + 1 < right) {
        let mid = Math.floor((left + right) / 2);
        if (numbers[mid] > numbers[right]) {
            left = mid;
        } else if (numbers[mid < numbers[right]]) {
            right = mid;
        } else {
            right--;
        }
    }
    if (numbers[left] < numbers[right]) {
        return numbers[left];
    } else {
        return numbers[right];
    }

};
```
