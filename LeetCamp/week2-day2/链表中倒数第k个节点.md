```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution:
    def getKthFromEnd(self, head: ListNode, k: int) -> ListNode:
        dummy = ListNode(0)
        dummy.next = head
        left, right = dummy, dummy
        for _ in range(k):
            right = right.next
        while right.next != None:
            right = right.next
            left = left.next
        return left.next
```        
