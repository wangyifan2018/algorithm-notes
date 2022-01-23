```py
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution:
    def getKthFromEnd(self, head: ListNode, k: int) -> ListNode:
        if not head:
            return head
        dummy = ListNode(0, head)
        left, right = dummy, dummy
        for _ in range(k):
            right = right.next
        while right.next:
            left = left.next
            right = right.next
        return left.next
```
