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
 * @return {number[][]}
 */
var levelOrder = function(root) {
    if (root == null) {
        return []
    }
    let q = [root], res = [];
    while (q.length) {
        size = q.length;
        tmp = []
        for (let i = 0; i < size; ++i) {
            x = q.shift();
            tmp.push(x.val);
            if (x.left) {q.push(x.left)}
            if (x.right) {q.push(x.right)}
        }
        res.push(tmp);
    }
    return res;
};
```
