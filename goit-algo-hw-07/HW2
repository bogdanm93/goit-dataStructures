# Enhanced version from task1 with added functionality to find the smallest value in the tree
class Node:
    def __init__(self, value):
        self.left_child = None
        self.right_child = None
        self.value = value

class BinaryTree:
    def __init__(self):
        self.root_node = None

    def insert_value(self, value):
        if self.root_node is None:
            self.root_node = Node(value)
        else:
            self._insert_recursively(self.root_node, value)
    
    def _insert_recursively(self, current_node, value):
        if value < current_node.value:
            if current_node.left_child is None:
                current_node.left_child = Node(value)
            else:
                self._insert_recursively(current_node.left_child, value)
        else:
            if current_node.right_child is None:
                current_node.right_child = Node(value)
            else:
                self._insert_recursively(current_node.right_child, value)

    def get_largest_value(self):
        if self.root_node is None:
            return None
        return self._find_largest(self.root_node)

    def _find_largest(self, node):
        current_node = node
        while current_node.right_child is not None:
            current_node = current_node.right_child
        return current_node.value

    def get_smallest_value(self):
        if self.root_node is None:
            return None
        return self._find_smallest(self.root_node)

    def _find_smallest(self, node):
        current_node = node
        while current_node.left_child is not None:
            current_node = current_node.left_child
        return current_node.value

# Example usage:
binary_tree = BinaryTree()
binary_tree.insert_value(20)
binary_tree.insert_value(10)
binary_tree.insert_value(30)
binary_tree.insert_value(5)
binary_tree.insert_value(15)

print("The largest value in the tree is:", binary_tree.get_largest_value())
print("The smallest value in the tree is:", binary_tree.get_smallest_value())