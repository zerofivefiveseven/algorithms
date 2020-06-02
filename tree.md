# Tree

 + [Validate Binary Search Tree](#validate-binary-search-tree)

## Validate Binary Search Tree

 https://leetcode.com/problems/validate-binary-search-tree/

 ```python
    def __init__(self, root):
        self.treeList=[] 
        if root is not None :
            cur=root
            self.treeList.append(cur)
        
            while cur.left is not None :
                self.treeList.append(cur.left)
                cur=cur.left

    def hasNext(self):
        if not self.treeList:
            return False
        else:
            return True
        
    def next(self):
        element=self.treeList.pop()
        if element.right is not None :
            self.treeList.append(element.right)
            tp = element.right
            while tp.left is not None :
                self.treeList.append(tp.left)
                tp = tp.left

        return element.val
 ```

 