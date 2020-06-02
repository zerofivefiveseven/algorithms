# Tree

 + [Subtree of Another Tree](#subtree-of-another-tree)
 
 ## Subtree of Another Tree

 https://leetcode.com/problems/subtree-of-another-tree/

 ```python
def isSubtree(self, tree, subt):
	if not tree and not subt:
		return True
	if not tree or not subt:
		return False
	
	if tree.val == subt.val and self.isSame(tree,subt):
		return True
	else:
		return self.isSubtree(tree.left, subt) or self.isSubtree(tree.right, subt)

def isSame(self, tree, subt):
	if not tree and not subt:
		return True
	elif not tree or not subt:
		return False
	elif tree.val != subt.val:
		return False
	else:
		return self.isSame(tree.left, subt.left) and self.isSame(tree.right, subt.right)
	
 ```