```java
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode(int x) { val = x; }
 * }
 */
class Solution {
    public ListNode deleteNode(ListNode head, int val) {
        if(head == null) return null;
        ListNode p = head;
        if(p.val == val)
        {
            head = head.next;
            return head;
        }
        while(p != null){
            if(p.next.val == val)
                break;
            p = p.next;
        }
        p.next = p.next.next;
        return head;

    }
}
```
