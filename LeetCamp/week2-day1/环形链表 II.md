```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution:
    def detectCycle(self, head: ListNode) -> ListNode:
        if head == None: return None
        if head.next == None: return None
        if head.next.next == None: return None

        slow = head.next
        fast = head.next.next

        while slow.next != None and fast.next != None:
            slow = slow.next
            fast = fast.next
            if fast.next != None:
                fast = fast.next
            else:
                return None
            if slow == fast:
                break
        
        if slow != fast:
            return None
        
        p = head
        while p != slow:
            p = p.next
            slow = slow.next
        
        return p
```        
