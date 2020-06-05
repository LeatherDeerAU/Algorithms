# Tree

+ [Binary Tree Inorder Traversal](#binary-tree-inorder-traversal)

##Binary Tree Inorder Traversal

https://leetcode.com/problems/binary-tree-inorder-traversal/

```python
def inorderTraversal(self, root: TreeNode) -> List[int]:
    curr = root
    stack = deque()
    ans = []
    while True:
        if curr:
            stack.append(curr)
            curr = curr.left
        else:
            if not stack:
                break
            curr = stack.pop()
            ans.append(curr.val)
            curr = curr.right
    return ans

```

