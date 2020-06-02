# Linked List

 + [Remove Nth Node From End of List](#remove-nth-node-from-end-of-list)
 
 ## Remove Nth Node From End of List

https://leetcode.com/problems/remove-nth-node-from-end-of-list/

 ```python
def removeNthFromEnd(self, head, n):
        slow = fast = self
        self.next = head
        while fast.next:
            if n:
                n -= 1
            else:
                slow = slow.next
            fast = fast.next
        slow.next = slow.next.next
        return self.next 
    
 ```