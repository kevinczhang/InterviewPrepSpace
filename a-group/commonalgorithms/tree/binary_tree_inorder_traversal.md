# Binary Tree Inorder Traversal

```java
/**
 * Definition for a binary tree node.
 * public class TreeNode {
 *     int val;
 *     TreeNode left;
 *     TreeNode right;
 *     TreeNode(int x) { val = x; }
 * }
 */
class Solution {
    public List<Integer> inorderTraversal(TreeNode root) {
        List<Integer> res = new ArrayList<>();
        if(root == null) return res;
        
        Stack<TreeNode> nodeStack = new Stack<TreeNode>();
        TreeNode curNode = root;
        
        while(!nodeStack.isEmpty() || curNode != null){
            if(curNode != null){
                nodeStack.push(curNode);
                curNode = curNode.left;
            } else {
                curNode = nodeStack.pop();
                res.add(curNode.val);
                curNode = curNode.right;
            }
        }
        
        return res;
    }
}
```

