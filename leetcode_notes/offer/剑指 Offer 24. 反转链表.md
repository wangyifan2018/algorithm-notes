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
    public ListNode reverseList(ListNode head) {
        if(head == null) return null;
        ListNode PNode = head;
        ListNode Pre = null;
        ListNode RevHead = null;

        while(PNode != null){
            ListNode Pnext = PNode.next;

            if(Pnext == null){
                RevHead = PNode;
            }
            PNode.next = Pre;
            Pre = PNode;
            PNode = Pnext;
        }
        return RevHead;
    }
}
```
