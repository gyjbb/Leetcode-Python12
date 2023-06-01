# Leetcode-Python12

## Binary tree theory, Recursion递归, (Iteration迭代)

May 25, 2023  4h

Congratulations!\
This is the twelfth day for leetcode python study. Today we will learn more about the Binary Tree!\
The challenges today are about the define and the preorder, inorder and post order traversals of the  binary tree.

## Binary tree theory
[Reading link](https://github.com/youngyangyang04/leetcode-master/blob/master/problems/%E4%BA%8C%E5%8F%89%E6%A0%91%E7%90%86%E8%AE%BA%E5%9F%BA%E7%A1%80.md)\
Binary tree are often associated with recursion.\
Here we need to learn about the kinds of binary trees, how to store, how to loop through, and the definition of binary tree.\
Priority queue is realized by a heap, and heap is a kind of binary tree, we can store and retrive data from it.\
The items in map and set are ordered, because the two data structures are realized by balanced binary search tree. But the unordered map and set are realized by hash table, and are not ordered.\
recursion 递归   stack\
iteration 迭代   queue\
前序遍历，中序遍历，后续遍历  都描述的是什么时候 遍历到中间的数。\
definition: binary tree is like linked list.
```python
class TreeNode:
    def __init__(self, val, left = None, right = Node):
        self.val = val
        self.left = left
        self.right = right
```

## Recursion递归
[reading](https://github.com/youngyangyang04/leetcode-master/blob/master/problems/%E4%BA%8C%E5%8F%89%E6%A0%91%E7%9A%84%E9%80%92%E5%BD%92%E9%81%8D%E5%8E%86.md)\
[video](https://www.bilibili.com/video/BV1Wh411S7xt/?spm_id_from=pageDriver&vd_source=63f26efad0d35bcbb0de794512ac21f3)\
Recursion is realized by stack.\
Think in the following 3 steps:
- 确定递归函数的参数和返回值;
- 确定终止条件
- 确定单层递归的逻辑
```python
# 前序遍历-递归-LC144_二叉树的前序遍历 Binary Tree Preorder Traversal
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def preorderTraversal(self, root: TreeNode) -> List[int]:
        if not root:
            return []

        left = self.preorderTraversal(root.left)
        right = self.preorderTraversal(root.right)

        return  [root.val] + left +  right
```
```python
# 中序遍历-递归-LC94_二叉树的中序遍历 Binary Tree Inorder Traversal
class Solution:
    def inorderTraversal(self, root: TreeNode) -> List[int]:
        if root is None:
            return []

        left = self.inorderTraversal(root.left)
        right = self.inorderTraversal(root.right)

        return left + [root.val] + right
```
```python
# 后序遍历-递归-LC145_二叉树的后序遍历  Binary Tree Postorder Traversal
class Solution:
    def postorderTraversal(self, root: TreeNode) -> List[int]:
        if not root:
            return []

        left = self.postorderTraversal(root.left)
        right = self.postorderTraversal(root.right)

        return left + right + [root.val]
```


## Iteration迭代
[reading1](https://github.com/youngyangyang04/leetcode-master/blob/master/problems/%E4%BA%8C%E5%8F%89%E6%A0%91%E7%9A%84%E8%BF%AD%E4%BB%A3%E9%81%8D%E5%8E%86.md)\
[reading2](https://github.com/youngyangyang04/leetcode-master/blob/master/problems/%E4%BA%8C%E5%8F%89%E6%A0%91%E7%9A%84%E7%BB%9F%E4%B8%80%E8%BF%AD%E4%BB%A3%E6%B3%95.md)



