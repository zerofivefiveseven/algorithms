# Tree

 + [Binary Tree Level Order Traversal](#binary-tree-level-order-traversal)
 
## Binary Tree Level Order Traversal

 https://leetcode.com/problems/binary-tree-level-order-traversal/

 ```python
def levelOrder(self, root):
	result = []
	self.level_dfs(root, 0, result)
	return result
	
def level_dfs(self, node, level, result):
	if not node:
		return
	if level == len(result):
		result.append([])
	result[level].append(node.val)
	self.level_dfs(node.left, level+1, result)
	self.level_dfs(node.right, level+1, result)
 ```