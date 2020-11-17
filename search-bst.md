### Iterative Solution
```
/**
 * Definition for a binary tree node.
 * function TreeNode(val, left, right) {
 *     this.val = (val===undefined ? 0 : val)
 *     this.left = (left===undefined ? null : left)
 *     this.right = (right===undefined ? null : right)
 * }
 */
/**
 * @param {TreeNode} root
 * @param {number} val
 * @return {TreeNode}
 */
var searchBST = function(root, val) {
    node = root
    while (node) {
        if (val == node.val) {
            return node
        } else if (val > node.val) {
            node = node.right
            continue
        } else {
            node = node.left
            continue
        }
    }
    
    return null
};
```
### Recursive Solution
```
var searchBST = function(root, val) {
    if (root) {
        if (val == root.val) {
            return root
        } else if (val > root.val) {
            return searchBST(root.right, val)
        } else {
            return searchBST(root.left, val)
        }
    } else {
        return null
    }
};
```
