# Tree

 + [Same Tree](#same-tree)
 
 ## Same Tree

 https://leetcode.com/problems/same-tree/

 ```python
def isSameTree(self, first, second):
        if first and second:
            return (first.val == second.val) and self.isSameTree(first.left, second.left) and self.isSameTree(first.right, second.right )
        elif not first and not second:
            return True
        else:
            return False     
 ```