# Tree

+ [Symmetric Tree](#symmetric-tree)

## Symmetric Tree

https://leetcode.com/problems/symmetric-tree/

```python
def isSymmetric(self, root: TreeNode) -> bool:
    if not root:
        return True

    def dfs(l, r):
        if not l and not r:
            return True
        if not l or not r or l.val != r.val:
            return False
        return dfs(l.left, r.right) & dfs(l.right, r.left)

    return dfs(root.left, root.right)

```