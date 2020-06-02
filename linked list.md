#Linked List

 + [Sort List](#sort-list)
 
 ## Sort List

 https://leetcode.com/problems/sort-list/

 ```python
def sortList(self, head):
        if not head or not head.next:
            return head
        fast, slow = head.next, head
        while fast and fast.next:
            fast = fast.next.next
            slow = slow.next
        second = slow.next
        slow.next = None
        left = self.sortList(head)
        right = self.sortList(second)
        return self.merge(left, right)
      
    def merge(self, left, right):
        if not left or not right:
            return left or right
        if left.val > right.val:
            left, right = right, left
        head = pre = left
        left = left.next
        while left and right:
            if left.val < right.val:
                left = left.next
            else:
                nxt = pre.next
                pre.next = right
                tmp = right.next
                right.next = nxt
                right = tmp
            pre = pre.next
        pre.next = left or right
        return head
 ```