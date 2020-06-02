# Linked List

 + [Linked List Cycle](#linked-list-cycle)
 
## Linked List Cycle

https://leetcode.com/problems/linked-list-cycle

 ```python
def hasCycle(self, head):
            slow = head
            fast = head
            while fast and fast.next:
                slow = slow.next
                fast = fast.next.next
                if slow == fast:
                    return True
            return False
 ```