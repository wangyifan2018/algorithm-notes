```python
/**
 * Definition for singly-linked list.
 * function ListNode(val) {
 *     this.val = val;
 *     this.next = null;
 * }
 */
/**
 * @param {ListNode} head
 * @return {ListNode}
 */
var reverseList = function(head) {
    let pre = null, pNext = null;
    while (head != null) {
        pNext = head.next
        head.next = pre
        pre = head
        head = pNext
    }
    return pre
};  
```
