# Inorder predecessor in Binary Search Tree

 The predecessor of a node x in a search tree is the node with largest key that belongs to the tree and that is strictly less than x’s key.

![Sample BST](../../../.gitbook/assets/image%20%2818%29.png)

In above binary search tree, in-order predecessor of 17 is 15 , predecessor of 6 is 4 and predecessor of 13 is 9.  


## If tree nodes have pointer to their parents

```java
public TreeNode withPointerToParent(TreeNode root, TreeNode x) {
		TreeNode predecessor = null;
		if(x.left != null) {
			predecessor = x.left;
			while(predecessor.right != null) {
				predecessor = predecessor.right;
			}			
		} else {
			predecessor = x.parent;
			while (predecessor != null && x == predecessor.left) {
				x = predecessor;
				predecessor = predecessor.parent;
			}
		}

		return predecessor;		
	}
```

## If tree nodes don't have pointer to their parents

```java
public TreeNode withoutPointerToParent(TreeNode root, TreeNode x) {
		TreeNode predecessor = null;
		if(x.left != null) {
			predecessor = x.left;
			while(predecessor.right != null) {
				predecessor = predecessor.right;
			}			
		} else {			
			while (root != null) {
				if(root.val == x.val)
					break;
				if(root.val < x.val) {
					predecessor = root;
					root = root.right;
				} else {
					root = root.left;
				}
			}
		}

		return predecessor;		
	}
```

