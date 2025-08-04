# 🧠 DSA Using Python

This repository contains clean, beginner-friendly implementations of core **Data Structures and Algorithms (DSA)** concepts using Python. Each concept is explored through interactive **Jupyter Notebooks**, making it ideal for both learning and revision.

---

## 📂 Contents

| Notebook | Description |
|----------|-------------|
| `dynamic_arrays.ipynb` | Implementation and explanation of dynamic arrays (like Python lists), their resizing logic, and performance trade-offs. |
| `Linked_List.ipynb` | Singly linked list with insertion, deletion, search, and traversal methods. |
| `stacks_using_arrays.ipynb` | Stack implementation using arrays (lists) with push/pop operations. |
| `stacks_using_linkedlists.ipynb` | Stack implementation using linked lists. |
| `queue_LL_implementation.ipynb` | Queue implementation using linked lists (enqueue, dequeue). |
| `searching_sorting.ipynb` | Classical searching (linear, binary) and sorting (bubble, selection, insertion, merge, quick sort) algorithms. |
| `hashing_linear_probing.ipynb` | Hash table implementation using linear probing for collision handling. |
| `hashing_via_chaining.ipynb` | Hash table implementation using chaining (linked lists) to handle collisions. |

---

# 🔗 Linked List in Python (Jupyter Notebook)

This notebook provides a complete walkthrough of **Linked List** implementation in Python from scratch — without using built-in data structures like `list` for core logic.

It’s great for beginners who want to understand how Linked Lists work internally, node-by-node, pointer-by-pointer.

---

## 💡 Concepts Covered

### ✅ 1. Node Structure
A `Node` class that stores:
- Data
- Pointer to the next node

### ✅ 2. LinkedList Class with Core Operations

#### Basic Setup
- `__init__()` → Initializes empty list
- `__len__()` → Number of nodes
- `__str__()` → Returns the LL as a string (e.g., `1->2->3`)

#### Insertion
- `insert_head(value)` → Insert at the beginning
- `append(value)` → Insert at the end
- `insert_after(after_value, value)` → Insert in the middle

#### Deletion
- `delete_head()` → Remove from the beginning
- `pop()` → Remove from the end
- `remove(value)` → Remove by value
- `delete_by_index(index)` → Remove by position

#### Searching
- `search(value)` → Search by value
- `__getitem__(index)` → Search by index (like `LL[2]`)

#### Utilities
- `traverse()` → Print all elements
- `clear()` → Empty the entire list

---

## 📌 Example Usage

```python
L = LinkedList()

# Insert from head
L.insert_head(1)
L.insert_head(2)

# Insert from tail
L.append(3)

# Insert in the middle
L.insert_after(2, 5)  # 2 -> 5 -> 1 -> 3

# Delete operations
L.delete_head()
L.pop()
L.remove(5)

# Accessing
print(L)            # View the linked list
print(L[1])         # Indexing
print(L.search(3))  # Find index of value

# Utility
len(L)
L.clear()
