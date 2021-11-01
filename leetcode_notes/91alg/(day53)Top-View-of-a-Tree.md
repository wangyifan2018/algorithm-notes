```python
class Solution:
    def solve(self, root):
        q = deque([(root, 0)])
        x = {}
        while q:
            (node, xval) = q.popleft()
            if xval not in x:
                x[xval] = node.val
            if node.left:
                q.append((node.left, xval - 1))
            if node.right:
                q.append((node.right, xval + 1))
        return [j for (i, j) in sorted(list(x.items()))]
```
