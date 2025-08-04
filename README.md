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

This notebook provides a full implementation of a **Singly Linked List** from scratch in Python, without relying on built-in data structures for internal logic. It’s designed to be educational, beginner-friendly, and hands-on.

---

## 🧱 Node Structure

Each node contains:
- `data`: The actual value
- `next`: A pointer to the next node in the list

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None
```

---

## 🧩 LinkedList Class with Core Operations

### 🔧 Basic Setup

| Method         | Description                            |
|----------------|----------------------------------------|
| `__init__()`   | Initializes an empty list              |
| `__len__()`    | Returns the number of nodes            |
| `__str__()`    | Returns the linked list as a string    |

---

### ➕ Insertion Methods

| Method                        | Description                        |
|-------------------------------|------------------------------------|
| `insert_head(value)`          | Insert at the beginning            |
| `append(value)`               | Insert at the end                  |
| `insert_after(after_value, value)` | Insert after a specified node     |

---

### ➖ Deletion Methods

| Method              | Description                     |
|---------------------|---------------------------------|
| `delete_head()`     | Remove from the beginning       |
| `pop()`             | Remove from the end             |
| `remove(value)`     | Remove a node by value          |
| `delete_by_index(index)` | Remove a node at a position |

---

### 🔍 Searching Methods

| Method             | Description                        |
|--------------------|------------------------------------|
| `search(value)`    | Returns index of the value         |
| `__getitem__(index)` | Access by index (like `LL[2]`)     |

---

### 🧰 Utility Methods

| Method       | Description                 |
|--------------|-----------------------------|
| `traverse()` | Prints all elements         |
| `clear()`    | Empties the entire list     |

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
```

---

## 🧠 Ideal For

- Beginners learning data structures  
- Practicing linked list logic without built-in types  
- Jupyter notebook-based visual exploration

---

## ✅ Dependencies

No external libraries needed — works in plain Python 3.

---

## 📁 File

- `Linked_List.ipynb` → Complete implementation with explanations and usage examples

---
