```py
class Solution:
    def isStraight(self, nums: List[int]) -> bool:
        nums.sort()
        cnt = 0
        for i in range(5):
            if nums[i] == 0:
                cnt += 1
                continue
            
            if i == 0:
                continue
            
            if nums[i - 1] == 0:
                continue

            if nums[i] == nums[i - 1]:
                return False
           
            if nums[i] - nums[i - 1] > 1  and nums[i] - nums[i - 1] - 1 <= cnt:
                cnt -= nums[i] - nums[i - 1] - 1
            elif nums[i] - nums[i - 1] > 1  and nums[i] - nums[i - 1] - 1 > cnt:
                return False


        return True
            

        
```   

```py

class Solution:
    def isStraight(self, nums: List[int]) -> bool:
        joker = 0
        nums.sort() # 数组排序
        for i in range(4):
            if nums[i] == 0: joker += 1 # 统计大小王数量
            elif nums[i] == nums[i + 1]: return False # 若有重复，提前返回 false
        return nums[4] - nums[joker] < 5 # 最大牌 - 最小牌 < 5 则可构成顺子

```
