# Tree

 + [Maximum Depth of Binary Tree](#maximum-depth-of-binary-tree)
 
 ## Maximum Depth of Binary Tree

 https://leetcode.com/problems/maximum-depth-of-binary-tree/

 ```python
def maxDepth(self, root):
            if not root:
                return 0
            return 1 + max(self.maxDepth(root.left), self.maxDepth(root.right))
 ```