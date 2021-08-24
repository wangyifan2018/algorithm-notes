```cpp
class Solution {
public:
    ListNode *detectCycle(ListNode *head) {
        ListNode* inLoop = getNodeInLoop(head);
        if (inLoop== nullptr) {
            return nullptr;
        }
        ListNode* slow = head;
        ListNode* fast = inLoop;   // 判断环时，快指针2k步，慢指针k步，相遇时，快指针比慢指针多走了n倍的环长度。可以用相遇的点初始化fast
        while (slow != fast) {
            slow = slow->next;
            fast = fast->next;
        }
        return slow;
    }

    ListNode* getNodeInLoop(ListNode* head) {
        if (head == nullptr || head->next == nullptr) {
            return nullptr;
        }
        ListNode* slow = head->next;   //避免头节点是环入口，先走一步
        ListNode* fast = slow->next;
        while (slow != nullptr && fast != nullptr) {
            if (slow == fast) {
                return slow;
            }
            if (fast->next == nullptr) {
                return nullptr;
            }
            slow = slow->next;
            fast = fast->next->next;
        }
        return nullptr;
    }
};

```
