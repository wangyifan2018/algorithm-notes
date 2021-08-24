```java
/**
 * Definition for a binary tree node.
 * public class TreeNode {
 *     int val;
 *     TreeNode left;
 *     TreeNode right;
 *     TreeNode(int x) { val = x; }
 * }
 */
class Solution {
    public TreeNode mirrorTree(TreeNode root) {
        if(root == null) return null;
        //if(root.left == null && root.right ==null) return null;

        TreeNode temp = root.left;
        root.left = root.right;
        root.right = temp;

        if(root.left != null)
            mirrorTree(root.left);
        if(root.right != null)
            mirrorTree(root.right);

        return root;
    }
}
```
