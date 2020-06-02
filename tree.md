# Tree

 + [Invert Binary Tree](#invert-binary-tree)
 
 ## Invert Binary Tree

 https://leetcode.com/problems/invert-binary-tree/

 ```python
def invertTree(self, root):
        if root == None:
            return None
        left = self.invertTree(root.left) 
        right = self.invertTree(root.right)
        root.right = left
        root.left = right
        return root         
 ```