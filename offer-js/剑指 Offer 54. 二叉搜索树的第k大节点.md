```py
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, x):
#         self.val = x
#         self.left = None
#         self.right = None

class Solution:
    def kthLargest(self, root: TreeNode, k: int) -> int:
        res = []
        def inorder(root):
            if not root:
                return
            
            inorder(root.left)
            res.append(root.val)
            inorder(root.right)
        
        inorder(root)
        return res[-k]
```

```py
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, x):
#         self.val = x
#         self.left = None
#         self.right = None

class Solution:
    def kthLargest(self, root: TreeNode, k: int) -> int:
        res, cnt = 0, 0
        def inorder(root):
            if not root:
                return
            nonlocal res, cnt
            inorder(root.right)
            cnt += 1
            if cnt == k:
                res = root.val
                return
            inorder(root.left)
        
        inorder(root)
        return res
```

```py
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, x):
#         self.val = x
#         self.left = None
#         self.right = None

class Solution:
    def kthLargest(self, root: TreeNode, k: int) -> int:
        def inorder(root):
            if not root:
                return
            inorder(root.right)
            if self.cnt == 0:
                return
            self.cnt -= 1
            if self.cnt == 0:
                self.res = root.val
                return
            inorder(root.left)
        
        self.cnt = k
        inorder(root)
        return self.res
```
