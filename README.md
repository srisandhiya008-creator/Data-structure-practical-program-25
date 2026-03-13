# Data-structure-practical-program-25# Node class for BST
class Node:
    def __init__(self, value):
        self.value = value
        self.left = None
        self.right = None

# Function to insert a node in BST
def insert(root, value):
    if root is None:
        return Node(value)
    
    if value < root.value:
        root.left = insert(root.left, value)
    else:
        root.right = insert(root.right, value)
    
    return root

# Preorder Traversal (Root -> Left -> Right)
def preorder(root):
    if root:
        print(root.value, end=" ")
        preorder(root.left)
        preorder(root.right)

# Main Program
root = None
values = [50, 30, 70, 20, 40, 60, 80]

# Inserting values into BST
for v in values:
    root = insert(root, v)

print("Preorder Traversal:")
preorder(root)
