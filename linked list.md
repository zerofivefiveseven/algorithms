# Linked List

 + [Reverse Linked List](#reverse-linked-list)
 
 ## Reverse Linked List

 https://leetcode.com/problems/reverse-linked-list/

 ```python
def reverseList(self, head: ListNode) -> ListNode: 
    prev = None
    cur = head
    while cur:
        tmp = cur.next
        cur.next = prev
        prev = cur
        cur = tmp
    return prev       
 ```