class TreeNode:
    def __init__(self, key):
        self.left = None
        self.right = None
        self.value = key

class BinarySearchTree:
    def __init__(self):
        self.root = None

    def insert(self, key):
        if self.root is None:
            self.root = TreeNode(key)
        else:
            self._insert_recursive(self.root, key)
    
    def _insert_recursive(self, node, key):
        if key < node.value:
            if node.left is None:
                node.left = TreeNode(key)
            else:
                self._insert_recursive(node.left, key)
        else:
            if node.right is None:
                node.right = TreeNode(key)
            else:
                self._insert_recursive(node.right, key)

    def find_maximum_value(self):
        if self.root is None:
            return None
        return self._find_maximum(self.root)

    def _find_maximum(self, node):
        current = node
        while current.right is not None:
            current = current.right
        return current.value

# Example usage:
bst = BinarySearchTree()
bst.insert(20)
bst.insert(10)
bst.insert(30)
bst.insert(25)
bst.insert(35)

print("The maximum value in the tree is:", bst.find_maximum_value())