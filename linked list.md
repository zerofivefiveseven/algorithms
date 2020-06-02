# Linked List

 + [Intersection of Two Linked Lists](#intersection-of-two-linked-lists)
 
 ## Intersection of Two Linked Lists

https://leetcode.com/problems/intersection-of-two-linked-lists/

 ```python
def getIntersectionNode(self, headA, headB):
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