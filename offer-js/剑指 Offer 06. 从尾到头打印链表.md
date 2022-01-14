```js
/**
 * Definition for singly-linked list.
 * function ListNode(val) {
 *     this.val = val;
 *     this.next = null;
 * }
 */
/**
 * @param {ListNode} head
 * @return {number[]}
 */
var reversePrint = function(head) {
    const res = []
    pNode = head
    while (pNode != null) {
        res.unshift(pNode.val)
        pNode = pNode.next
    }
    return res
};
```
