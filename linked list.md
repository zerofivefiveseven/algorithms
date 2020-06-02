# Linked List

 + [Linked List Cycle II](#linked-list-cycle-ii)
 
 ## Linked List Cycle II

https://leetcode.com/problems/linked-list-cycle-ii/

 ```python
def detectCycle(self, head):
    slow = head
    fast = head
    node = head
    while fast and fast.next:
        slow = slow.next
        fast = fast.next.next
        if slow == fast:
            while node != slow:
                slow = slow.next
                node = node.next
            return node
    return None
    
 ```