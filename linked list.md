# Linked List

 + [Middle of The Linked List](#middle-of-the-linked-list)
 
 ## Middle of The Linked List

https://leetcode.com/problems/middle-of-the-linked-list/

 ```python
def middleNode(self, head):
    slow = fast = head
    while fast and fast.next:
        slow = slow.next
        fast = fast.next.next
    return slow    
 ```
