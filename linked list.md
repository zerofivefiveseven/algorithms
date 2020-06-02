# Linked List

 + [Reorder List](#reorder-list)
 
## Reorder List

https://leetcode.com/problems/reorder-list

 ```python
def reorderList(self, head):
        if not head or not head.next:
            return
        
        slow, fast = head, head
        while fast and fast.next:
            slow = slow.next
            fast = fast.next.next
        
        prev, slow.next, slow = None, None, slow.next
        while slow:
            prev, prev.next, slow = slow, prev, slow.next

        slow = head
        while prev:
            slow.next, slow = prev, slow.next
            prev.next, prev = slow, prev.next
 ```
