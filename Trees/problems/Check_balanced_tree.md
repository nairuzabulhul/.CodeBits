### Write a program to check if a tree is balanced or not

```
# Definition for a binary tree node.
# class TreeNode(object):
#     def __init__(self, x):
#         self.val = x
#         self.left = None
#         self.right = None
class Solution:
    # @param {TreeNode} root
    # @return {boolean}

    def validate(self, root):
        if root == None:
            return 0

        leftHeight = self.validate(root.left)
        
        if leftHeight == -1:
            return -1

        rightHeight = self.validate(root.right)
        if rightHeight == -1:
            return -1

        heightDiff = abs(leftHeight - rightHeight)
        if heightDiff > 1:
            return -1
        else:
            return max(leftHeight,rightHeight)+1


    def isBalanced(self, root):
        if self.validate(root) == -1:
            return False
        else:
            return True

```
