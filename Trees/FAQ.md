# RIGHT ROTATION - Algorithm of Left Left (LL) Condition

def right_rotate(unbalanced_node):
    new_root = unbalanced_node.left
    unbalanced_node.left = unbalanced_node.left.right
    new_root.right = unbalanced_node
    #update height and newroot
    #return newroot


unbalanced_node.left = unbalanced_node.left.right, this is setting it to None

but why not just set it to = None?

# Why unbalanced_node.left = new_root.right?
This step ensures that if new_root.right (initially y.right) is not None, it is correctly attached to unbalanced_node. If y.right is None, it effectively means unbalanced_node.left becomes None, which is necessary for the rotation to maintain the tree structure and balance.

By not directly setting unbalanced_node.left to None, this code handles the general case where new_root.right might not be None. In other words, it allows for the possibility of a more complex subtree being involved in the rotation.

If you set unbalanced_node.left to None directly, you would lose any subtree that might exist there. The current approach preserves the structure of the tree correctly, even in cases where new_root.right is not None.