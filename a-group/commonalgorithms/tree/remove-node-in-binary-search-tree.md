# Remove Node in BST

Given a root of Binary Search Tree with unique value for each node. Remove the node with given value. If there is no such a node with given value in the binary search tree, do nothing. You should keep the tree still a binary search tree after removal.

## Solution

```java
/**
 * Definition of TreeNode:
 * public class TreeNode {
 *     public int val;
 *     public TreeNode left, right;
 *     public TreeNode(int val) {
 *         this.val = val;
 *         this.left = this.right = null;
 *     }
 * }
 */
public class Solution {
    /**
     * @param root: The root of the binary search tree.
     * @param value: Remove the node with given value.
     * @return: The root of the binary search tree after removal.
     */
    public TreeNode removeNode(TreeNode root, int value) {
        if(root == null) return null;
        if(root.val == value) return replaceNode(root);
        
        TreeNode parent = root;
        TreeNode current = (value < root.val) ? root.left : root.right;
        
        while(current != null){
            if(current.val == value){
                if(current == parent.left){
                    parent.left = replaceNode(current);
                } else {
                    parent.right = replaceNode(current);
                }
                return root;
            } else {
                parent = current;
                current = (value < current.val) ? current.left : current.right;
            }
        }
        return root;
    }
    
    TreeNode replaceNode(TreeNode node){
        if(node.left == null && node.right == null) return null;
        if(node.left != null && node.right == null) return node.left;
        if(node.left == null && node.right != null) return node.right;
        
        TreeNode parent = node, current = node.right;
        while(current.left != null){
            parent = current;
            current = current.left;
        }
        
        if(node.right == current){
            current.left = node.left;
        } else {
            parent.left = current.right;
            current.right = node.right;
            current.left = node.left;
        }
        return current;
    }
}

```

