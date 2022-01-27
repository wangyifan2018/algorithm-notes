```py
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def pathSum(self, root: TreeNode, target: int) -> List[List[int]]:
        res = []
        if not root:
            return res
        
        def dfs(root, tmp, res):
            if not root:
                return
            tmp.append(root.val)
            if not root.left and not root.right:
                if sum(tmp) == target:
                    res.append(tmp.copy())
            dfs(root.left, tmp, res)
            dfs(root.right, tmp, res)
            tmp.pop()
        
        dfs(root, [], res)

        return res

```
