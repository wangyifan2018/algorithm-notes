```py
class Solution:
    def movingCount(self, m: int, n: int, k: int) -> int:
        q, visited = [(0, 0, 0, 0)], set()
        while q:
            i, j, si, sj = q.pop(0)
            if i >= m or j >= n or k < si + sj or (i, j) in visited: continue
            visited.add((i, j))
            q.append((i + 1, j, si + 1 if (i + 1) % 10 else si - 8, sj))
            q.append((i, j + 1, si, sj + 1 if (j + 1) % 10 else sj - 8))
        return len(visited)

```
