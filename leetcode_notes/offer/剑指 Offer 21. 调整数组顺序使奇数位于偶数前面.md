```java
class Solution {
    public int[] exchange(int[] nums) {
        int low = 0, high = nums.length - 1, temp = 0;
        while (low < high){
            while(low < high && (nums[low] % 2 == 1)){
                low ++;
            }
            while(low < high && (nums[high] % 2 == 0)){
                high--;
            }

            temp = nums[low];
            nums[low] = nums[high];
            nums[high] = temp;
        }
        return nums;
    }
}
```
