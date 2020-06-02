# Tree

 + [Symmetric Tree](#symmetric-tree)
 
 ## Symmetric Tree

 https://leetcode.com/problems/symmetric-tree/

 ```python
def isEqual(self, l, r):
	if not l and not r:
		return True
	if not l or not r:
		return False
	return l.val == r.val and self.isEqual(l.left, r.right) and self.isEqual(l.right, r.left)

def isSymmetric(self, root: TreeNode):
	if not root:
		return True
	if self.isEqual(root.left, root.right):
		return True

 ```