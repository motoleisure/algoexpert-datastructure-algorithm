## Brach Sums
- 题目：Write a function that takes in a Binary Tree and returns **a list of its branch sums** ordered from leftmost branch sum to right most brach sum.
- A branch sum is the sum of all values in a Binary Tree branch. A Binary Tree branch is a path of nodes in a tree that starts at the root node and ends as any leaf node.
- Each **Binary Tree** node has an integer **value**, a **left** child node, and a **right** child node. Children nodes can either be **BinaryTree** nodes themselves or **None/null**.

- **Sample Input**
```python
    1
   / \
  2   2
 / \ / \
3  4 4  3
```
- **Sample Output**
```python
[6, 7, 7, 6]
```

### Solutions
#### Solution 1, 问题说的是要返回从左到右，从root到leaf node的sum的list. 这用到的是dfs。
- Time : O(n) | Space : O(n)
```python
# This is the class of the input root. Do not edit it.
class BinaryTree:
    def __init__(self, value):
        self.value = value
        self.left = None
        self.right = None

def branchSums(root):
    # Write your code here.
    bsum = []
    dfs(root, 0, bsum)
    return bsum

def dfs(node, runningsum, bsum):
    if node is None:
        return

    newRunningsum = runningsum + node.value
    if not (node.left or node.right):
        bsum.append(newRunningsum)
        return

    dfs(node.left, newRunningsum, bsum)
    dfs(node.right, newRunningsum, bsum)
```

## 解题核心思想
### blabla
