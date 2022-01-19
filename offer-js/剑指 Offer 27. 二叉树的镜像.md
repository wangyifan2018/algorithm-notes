```js
/**
 * Definition for a binary tree node.
 * function TreeNode(val) {
 *     this.val = val;
 *     this.left = this.right = null;
 * }
 */
/**
 * @param {TreeNode} root
 * @return {TreeNode}
 */
var mirrorTree = function(root) {
    if (root == null) {
        return root;
    }

    const right = mirrorTree(root.right);
    const left = mirrorTree(root.left);

    root.left = right;
    root.right = left;

    return root;
};
```
