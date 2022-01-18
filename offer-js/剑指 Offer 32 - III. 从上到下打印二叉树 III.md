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
        let size = q.length;
        let tmp = [];
        for (let i = 0; i < size; ++i) {
            let x = q.shift();
            if (res.length % 2 == 0) {tmp.push(x.val)}
            if (res.length % 2 != 0) {tmp.unshift(x.val)}
            if (x.left) {q.push(x.left)}
            if (x.right) {q.push(x.right)}
        }
        res.push(tmp)
    }
    return res
};
```
