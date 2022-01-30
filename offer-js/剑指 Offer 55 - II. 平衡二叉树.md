```py
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, x):
#         self.val = x
#         self.left = None
#         self.right = None

class Solution:
    def isBalanced(self, root: TreeNode) -> bool:
        if not root:
            return True
        res = True

        def dfs(root):
            if not root:
                return 0
            
            left = dfs(root.left)
            if left == -1: return -1
            right = dfs(root.right)
            if right == -1: return -1

            return -1 if abs(left - right) > 1 else max(left, right) + 1

        return dfs(root) != -1
```        
