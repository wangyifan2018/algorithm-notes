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
