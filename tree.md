# Tree

 + [Validate Binary Search Tree](#validate-binary-search-tree)

## Validate Binary Search Tree

 https://leetcode.com/problems/validate-binary-search-tree/

 ```python
def isValidBST(self, root):
	if not root:
		return True
	def inorder(root):
		if root.left:
			inorder(root.left)
		ans.append(root.val)
		if root.right:
			inorder(root.right)
	ans = []
	inorder(root)
	if sorted(ans) == ans and len(set(ans)) == len(ans) :
		return True
	return False
 ```

 