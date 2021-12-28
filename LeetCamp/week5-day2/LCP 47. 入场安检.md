```python
class Solution:
    def securityCheck(self, capacities: List[int], k: int) -> int:
        MOD = 10 ** 9 + 7
        n = len(capacities)

        #----背包问题，不需要逆序
        dp = [[0 for _ in range(k + 1)] for _ in range(n + 1)]
        dp[0][0] = 1         
        for i in range(1, n + 1):
            for peo in range(0, k + 1):
                dp[i][peo] = dp[i - 1][peo]
                if peo >= capacities[i - 1] - 1:
                    dp[i][peo] += dp[i - 1][peo - (capacities[i - 1] - 1)]
            dp[i][peo] %= MOD

        return dp[n][k]
```
