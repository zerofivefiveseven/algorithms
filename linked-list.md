# Linked List

 + [Reverse Linked List](#reverse-linked-list)
 + [Middle of The Linked List](#middle-of-the-linked-list)
 + [Palindrome Linked List](#palindrome-linked-list)
 + [Merge Two Sorted Lists](#merge-two-sorted-lists)
 + [Remove Nth Node From End of List](#remove-nth-node-from-end-of-list)
 + [Linked List Cycle II](#linked-list-cycle-ii)
 + [Linked List Cycle](#linked-list-cycle)
 + [Reorder List](#reorder-list)
 + [Intersection of Two Linked Lists](#intersection-of-two-linked-lists)
 
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

## Middle of The Linked List

https://leetcode.com/problems/middle-of-the-linked-list/

 ```python
def middleNode(self, head: ListNode) -> ListNode:
    slow = fast = head
    while fast and fast.next:
        slow = slow.next
        fast = fast.next.next
    return slow    
 ```

## Palindrome Linked List

https://leetcode.com/problems/palindrome-linked-list/

 ```python
def isPalindrome(self, head):
    rev = None
    slow = fast = head
    while fast and fast.next:
        fast = fast.next.next
        rev, rev.next, slow = slow, rev, slow.next
    if fast:
        slow = slow.next
    while rev and rev.val == slow.val:
        slow = slow.next
        rev = rev.next
    return not rev
 ```

## Merge Two Sorted Lists

https://leetcode.com/problems/merge-two-sorted-lists/

 ```python
def mergeTwoLists(self, l1: ListNode, l2: ListNode) -> ListNode:
    if not l1 or not l2:
        return l1 or l2
    if l1.val < l2.val:
        l1.next = self.mergeTwoLists(l1.next, l2)
        return l1
    else:
        l2.next = self.mergeTwoLists(l1, l2.next)
        return l2
    
 ```

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

## Linked List Cycle II

https://leetcode.com/problems/linked-list-cycle-ii/

 ```python
def detectCycle(self, head: ListNode) -> ListNode:
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

## Linked List Cycle

https://leetcode.com/problems/linked-list-cycle

 ```python
def hasCycle(self, head: ListNode) -> bool:
            slow = head
            fast = head
            while fast and fast.next:
                slow = slow.next
                fast = fast.next.next
                if slow == fast:
                    return True
            return False
 ```

## Reorder List

https://leetcode.com/problems/reorder-list

 ```python
def reorderList(self, head: ListNode) -> None:
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

## Intersection of Two Linked Lists

https://leetcode.com/problems/intersection-of-two-linked-lists/

 ```python
def getIntersectionNode(self, headA: ListNode, headB: ListNode) -> ListNode:
        temp1 = headA
        temp2 = headB
        d = {}
        while temp1:
            d[temp1] = temp1
            temp1 = temp1.next
        while temp2:
            if temp2 in d:
                return temp2
            temp2 = temp2.next
        return None
 ```