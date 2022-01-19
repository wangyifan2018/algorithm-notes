```js
/**
 * Definition for a binary tree node.
 * function TreeNode(val) {
 *     this.val = val;
 *     this.left = this.right = null;
 * }
 */
/**
 * @param {TreeNode} A
 * @param {TreeNode} B
 * @return {boolean}
 */
var isSubStructure = function(A, B) {
    function dfs(root1, root2) {
        if (root2 == null) {
            return true;
        }
        if (root1 == null ) {
            return false;
        }
        if (root1.val !== root2.val) {
            return false;
        }
        return dfs(root1.left, root2.left) && dfs(root1.right, root2.right);
    }

    return Boolean(A && B) && (dfs(A, B) || isSubStructure(A.left, B) || isSubStructure(A.right, B));


};
```
