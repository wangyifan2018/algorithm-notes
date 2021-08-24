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
    public ListNode getKthFromEnd(ListNode head, int k) {
        if(head == null || k == 0)
            return null;
        
        ListNode Ahead = head;
        ListNode Behind = head;

        for(int i = 0; i < k - 1; i++){
            if(Ahead != null){
                Ahead = Ahead.next;
            }
            else{
                return null;
            }
        }

        while(Ahead.next != null){
            Ahead = Ahead.next;
            Behind = Behind.next;
        }

        return Behind;
    }
}
```
