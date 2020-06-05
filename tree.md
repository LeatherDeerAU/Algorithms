# Tree

+ [Maximum Depth of Binary Tree](#maximum-depth-of-binary-tree)

##Maximum Depth of Binary Tree


https://leetcode.com/problems/maximum-depth-of-binary-tree/#

 ```python
def maxDepth(self, root):
    return self.max_depth_recursive(root, 0)
def max_depth_recursive(self, root, max_depth):
    if not root:
        return max_depth
    return max(self.max_depth_recursive(root.left, max_depth + 1),
               self.max_depth_recursive(root.right, max_depth + 1))

 ```

